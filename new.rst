
工具选择
~~~~~~~~~~~
常用的抓取手段一般选择编写脚本如Python等语言。本人对脚本不是特别擅长，为此选择先寻找其他人提供的脚本。网上公开的脚本也不少，经过调研有以下几类：
scrapy：::
	# -*- coding: utf-8 -*-
  # coding=utf-8
  import json
  import scrapy
  
  class PositionSpider(scrapy.Spider):
      name = "position"
      # allowed_domains = ["lagou.com/zhaopin/"]
      start_urls = [
          'https://www.lagou.com/jobs/positionAjax.json']
  -------------
      totalPageCount = 0
      curpage = 1
      city = u'杭州'
      district = u'西湖区'
      url = 'https://www.lagou.com/jobs/positionAjax.json'
  -------------
      # 设置下载延时
      # download_delay = 10
  -------------
      def start_requests(self):
      def parse(self, response):
          # print response.body
          print response.body.decode('utf-8')
          print str(self.curpage) + "page"
  -------------
          jdict = json.loads(response.body)
          jcontent = jdict['content']
          jposresult = jcontent["positionResult"]
          pageSize = jcontent["pageSize"]
          jresult = jposresult["result"]
          self.totalPageCount = jposresult['totalCount'] / pageSize + 1;
          for each in jresult:
              print each['city']
              print each['companyFullName']
              print each['companySize']
              print each['positionName']
              print each['secondType']
              print each['salary']
              print ''
  -------------
          if self.curpage <= self.totalPageCount:
              self.curpage += 1
              yield scrapy.http.FormRequest(self.url, formdata={'pn': str(self.curpage), 'city': self.city,'district': self.district},
                                                     callback=self.parse)
