## HTML Tables

```html
<table>
    <tr>
        <th>Dates</th>
        <th>Careers</th>
    </tr>

    <tr>
        <td>2014</td>
        <td>Student</td>
    </tr>
</table>   
```

```html
<table>
    <thead>
    </thead>

    <tbody>
    </tbody>

    <tfoot>
    </tfoot>
</table>
```

```html
<table>
      <thead>
        <tr>
            <th>年度</th>
            <th>內容</th>
        </tr>
      </thead>

      <tbody>
      <tr>
        <td>2018-2020</td>
        <td>中山大學產碩專班</td>
      </tr>
      <tr>
        <td>2020-2022</td>
        <td>台新國際商銀 模型分析師</td>
      </tr>
      </tbody>

      <tfoot>
      </tfoot>

    </table>
```



- 區分出thead, tbody, tfoot這些結構是為了方便個別進行其他自定義調整（例如凍結first row）
- html tag之中，牽扯到風格定義的attribute不建議使用，例如:bgcolor, frame, align，因為這是交給css的事
- recap: html結構, css風格, javascript行為
- `tr`: table row
- `td`: table data

## Using HTML Tables for Layout

- 因為還沒學css，可以使用table來切版，編排文字和圖片的位置
  
```html
 <table>
        <tr>
        <td><img src='img/me.jpg'></td>
        <td>
            <h1>劉冠廷</h1>     
            <p><em>創作者</em></p>
            <p>數位產品、資料科學、投資</p>
        </td>
        </tr>
</table>
``` 

## How to type emoji

- Mac: cmd+ctrl+space

## Other Table tricks

- 做出一個row和兩個col，裡面再各塞一個table
- 不太建議這樣做，不過當作一個冷知識


```html
<table>  
    <tbody>
    <tr>
        <td>
        <table>
            <tr>
                <td>Python</td>
                <td>*****</td>
            </tr>
            <tr>
            <td>Photography</td>
            <td>***</td>
        </tr>
        </table>
        </td>

        <td>
        <table>
            <tr>
                <td>Investing</td>
                <td>*****</td>
            </tr>
            <tr>
                <td>Machine Learning</td>
                <td>***</td>
            </tr>
        </table>

        </td>       
    </tr>
    </tbody>    
</table>
```

## HTML FORM

- label和input可以互搭
- input裡面的type可以有不同形式
  - 選日期、提交鈕、搜尋、密碼輸入...
- 學了JS才能發揮form的真正威力，但是現在可以先用基本的`mailto`，submit時能開啟email應用程式，並把submit內容自動謄上去

```html
<form action="mailto:ke0006123@gmail.com", method="POST", enctype="text/plain">
    <label for="">尊姓大名</label>
    <input type="text" name="urNAME" id="">
    <br>
    <label for="">你的伊媚兒</label>
    <input type="email" name="urEMAIL" id="">
    <br>
    <input type="submit" value="交上飲水小卡">
</form>
```

## 把個人網頁推上去

- hosting服務可以用godaddy或是bluehost，但是現在對我們還太進階，而且要付錢
- 可以用Github，創一個repo，把html傳上去，從setting變成github pages

