## Jenkins config


chú ý chính tả phần jenkins file.  <br/>
Setting project thường là Jenkinsfile. <br/>
Thì ở trong code repo phải để là Jenkinsfile , ko thì sẽ bị lỗi ko  tìm thấy  file jenkins


##### React test

1 Check convention code with eslint

Install eslint  : https://dev.to/knowankit/setup-eslint-and-prettier-in-react-app-357b





2 Jest test


```
in package json 　để dòng scrip này mục đich là ko có prompt khi chạy test
 "test-cicd": "CI=true react-scripts test --env=jsdom",
```


run test
```
npm run test-cicd
```





##### Note

npm thì chạy các package  global. còn npx chị các  packages không global ( có thể chỉ trong 1 folder)
Ví dụ chạy lint``` npm lint src``` sẽ không được mà chạy ``` npx lint src```  lại được