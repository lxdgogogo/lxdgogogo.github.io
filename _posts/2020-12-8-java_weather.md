---
layout: post
title: 用fastjson实现天气温度的获取
categories: 安卓开发, 天气
description: myself
keywords: lxd
---

## 在Android Studio环境下获取天气的温度

## 需求  

在开发智能寝室的设计时，想在安卓手机上可以获取温度湿度等信息，网上有一些方法，我用的时候出现了很多坑，本文章用于给大家排坑

## 下载jar包  

由于需要解析json文件，因此需要在 <https://sourceforge.net/projects/fastjson/files/> 中下载阿里巴巴最新版本的fastjson，然后将其放在Projects/app/libs的目录下即可

## 找到天气网站api  

我借助的是<https://www.sojson.com/blog/305.html>里面查询的天气接口，可以知道如何找到对应城市的json文件

## 解析并获得温度  

我这里需要的是温度的数值，因此代码里只输出了温度的数值。需要其他的数值可以自行修改，代码中json1就是经解析得到的json文件

    public class ExampleUnitTest {

        private String dealResponseResult(InputStream inputStream) {
            StringBuilder html = new StringBuilder();      //存储处理结果
            try {
                InputStreamReader inputStreamReader = new InputStreamReader(inputStream);
                BufferedReader reader = new BufferedReader(inputStreamReader);
                html.append(reader.readLine());
            } catch (IOException e) {
                e.printStackTrace();
            }
            return html.toString();
        }
        @Test
        public int get_temperature() {
            try {
                URL url = new URL("http://t.weather.itboy.net/api/weather/city/101050101");
                HttpURLConnection connection = (HttpURLConnection) url.openConnection();
                connection.setRequestMethod("GET");
                connection.setConnectTimeout(5 * 1000);
                connection.setReadTimeout(5 * 1000);
                connection.connect();
                //获得服务器的响应码
                int response = connection.getResponseCode();
                if (response == HttpURLConnection.HTTP_OK) {
                    InputStream inputStream = connection.getInputStream();
                    String html = dealResponseResult(inputStream);
                    JSONObject json = JSONObject.parseObject(html);
                    JSONObject json1 = json.getJSONObject("data");
                    int temp =  Integer.parseInt(json1.getString("wendu"));
                    System.out.println(temp);
                    return temp;
                }
            } catch (Exception e) {
                e.printStackTrace();
            }
            return -1;
        }
    }
