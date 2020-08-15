<template>
  <div class="discription">
      <h2>
          چکیده قلعه فلک الفلاک
      </h2>
      <div>
        <p>
            {{description}}
        </p>    
            <ul>
                <li>
                    <span>نام</span>
                    <ol>قلعه فلک الفلاک</ol>
                </li>
                <li>
                    <span>واژه شناسی</span>
                    <ol>فلک الفلاک در لغت به معنای سپهر سپهران است</ol>
                </li>
                <li>
                    <span>وجه تسمیه</span>
                    <ol>با توجه به اینکه ممکن است دوازده برجی اشاره ای به دوازده برج فلکسباشد ممکن است نام فلک الفلاک نیز از همین جا ریشه گرفته باشد.</ol>
                </li>
                <li>
                    <span>قدمت</span>
                    <ol>دوره ساسانی . در دوران صفوی و قاجار نیز الحاقاتی به این قلعه اضافع شد</ol>
                </li>
                <li>
                    <span>باز سازی</span>
                    <ol>1389</ol>
                </li>
                <li>
                    <span>ویژگی خاص</span>
                    <ol>زیبایی و معماری شگفت انگیزاین قلعه موجب شده کهاین قلعه از سوی بسیاری از کارشناسان به عنوان یکی از شاهکارهای مهندسی و معماری دنیا باشد.
                    </ol>
                </li>

            </ul>
      </div>   
  </div>
</template>

<script>
export default {
    name:"Discription",
    props:['description']
}
</script>


<style>
.discription{
    padding: 10px 5%;
    margin: 10px 10%;
    background-color: rgb(251, 245, 234);
    direction: rtl;
    border: rgb(170, 170, 156) solid 1px;
}
.discription h2{
    color: rgb(131, 81, 25);
    padding: 10px 10px;
    
}
.discription ol{
    color: rgb(80, 55, 9);
    font-size: 1.1em;
    margin-top: 5px;

}

.discription span{
    background-color:rgb(83, 75, 75);
    font-size: 1.2em;
    padding-right: 10px;
    display:block;
    color: ivory;
    margin-left:200px ;
}
.discription span:hover{
    background-color:rgba(83, 75, 75,0.6);
}
.discription li{
    margin-bottom: 10px;
    
    }
</style>