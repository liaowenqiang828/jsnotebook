```
CSS（一）实战:

HTML文件
*******************************************************************************************************************

<!DOCTYPE>
<html>
  <head>
    <title>CSS(一)实战</title>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="css(1).css" type="text/css"/>
  </head>
  
  <body>
    <div class="up-title">
      <p>Saint Petersburg</p>
    </div>

    <ul>
      <li class="div">
        <div class="like"></div>
        <p><a href="https://school.thoughtworks.cn">Like</a></p>
      </li>

      <li>
        <div class="favorites"></div>
        <p><a href="https://school.thoughtworks.cn">Favorites</a></p>
      </li>

      <li>
        <div class="discuss"></div>
        <p><a href="https://school.thoughtworks.cn">Discuss</a></p>
      </li>
    </ul>

  </body>
</html>

*******************************************************************************************************************
CSS 文件：

* {
  padding: 0;
  margin: 0;
}

html body {
  height: 100%;
  
  margin: 0;
  padding: 0;
}

.up-title {
  position: relative;
  top: calc(50vh - 240px);
  left: calc(50vw - 225px);

  height: 100px;
  width: 480px;

  border-radius: 20px;
  background: red;
}

ul{
  position: relative;
  top: calc(50vh - 240px + 50px);
  left: calc(50vw - 225px);

  height: 300px;  
  width: 480px;

  border-radius: 20px;
  background-color: red;
}

li {
  display: flex;
  height: 100px;
}

li div.like {
  list-style-type: none;
  color: aliceblue;

  background-image: url(/home/lwq/下载/CSS素材.png);
  background-position: 5px -65px;
  background-repeat: no-repeat;
}

li div.favorites {
  list-style-type: none;
  color: aliceblue;

  background-image: url(/home/lwq/下载/CSS素材.png);
  background-position: -88px  7px;
  background-repeat: no-repeat;
}

li div.discuss {
  list-style-type: none;
  color: aliceblue;

  background-image: url(/home/lwq/下载/CSS素材.png);
  background-position: 8px  8px;
  background-repeat: no-repeat;
}

li p {
  margin-left: 20px;
  margin-top: 25px;
  padding-top: 10px;
  font-size: 30;
  text-align: left;
  color: aliceblue;
}

div p {
  margin-left: 60px;
  padding-top: 25px;
  font-size: 40;
  text-align: left;
  color: aliceblue;
}

li div {
  height: 60px;
  width: 60px;
   
  margin-top: 20px;
  margin-left: 20px;
}

a {
  text-decoration: none;
  color: aliceblue;
}
```