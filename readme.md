## Jenkins config


chú ý chính tả phần jenkins file.  <br/>
Setting project thường là Jenkinsfile. <br/>
Thì ở trong code repo phải để là Jenkinsfile , ko thì sẽ bị lỗi ko  tìm thấy  file jenkins


##### React test

1 Jest test


```
in package json 　để dòng scrip này mục đich là ko có prompt khi chạy test
 "test-cicd": "CI=true react-scripts test --env=jsdom",
```


