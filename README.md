# HW2blog
[Demo](https://chunzel16.github.io/HW2demo/index.html)
For homework2, I need use javascript and jQuery to design a page for simple calculating
## Create a new branch
At first, I create a new branch called HW2-feature
```
git branch HW2-feature
git checkout HW2-feature

```
## design
I want to make a webpage that you can choose the shoes and your size, I will help you to calculate the price that you need to pay.
At first, adding two pictures in the page
```
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!--Bootstrap CSS-->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
        
        
      <link rel="stylesheet" type="text/css" href="styles.css">

    <title>Shoes</title>
  </head>
    <body>
    <div class="container" id="banner">
        <h1>Shoes</h1>
    </div>
        <div class="pagebackground">    
        <div class="container">
            <div class="content">
               <h2>We have two shoes for you</h2>
                  <div class="row">
                        <div class="col-md-6">
                            <img class="img-responsive" src="images/chicago.jpg" alt="Chicago">
                        </div>

                        <div class="col-md-6">
                            <img class="img-responsive" src="images/bred.jpg" alt="Bred" >
                        </div>
                    </div> 
            </div>
        </div>
    </div> 
    ```
    Then, adding sonecessary elements.
     ```
     <div class="container outer">
            <h2>Calculating price</h2>
            <div class="container inner">
                <div class="row">
                    <div class="col-xs-12">
                        <p>Choose a type of shoes, Chicago or Bred, and choose a size, I will let you know the price</p>
                    </div>
                </div>
                <hr>
                <form id="type">
                    <div class="row">
                        
                            <div class="col-sm-6">
                                <h3>Shoes Type</h3>
                                    <div class="inside">
                                        <input type="radio" name="shoetype" value="1.2" id="chicago" checked="checked">
                                        <label for="chicago">Chicago</label>

                                        <input type="radio" name="shoetype" value="1" id="bred">
                                        <label for="bred">Bred</label>
                                    </div>
                        </div>
                        <div class="col-sm-6">
                                    <h3>Choose Your Size</h3>
                                    <div class="inside">
                                        <input type="radio" name="size" value="450" id="9.5" checked="checked"><label for="9.5">9.5</label>

                                        <input type="radio" name="size" value="475" id="10"><label for="10">10</label>

                                        <input type="radio" name="size" value="430" id="10.5"><label for="10.5">10.5</label>

                                        <input type="radio" name="size" value="425" id="11"><label for="11">11</label>
                                    </div>
                        </div>
                    </div>
                    <hr>
               <div class="row">
                        <div class="col-sm-12 text-center">
                            <input type="submit" id="button" onclick="return pricecalculation()"><Lable for="button">submit</Lable>
                        </div>
                    </div>
                </form>
                <hr>
                <h2>Price</h2>
                <div class="output">
                    <div class=row>
                    <div class="col-sm-12">
                        <table class="table" id="price">
                            <thead>
                                <tr>
                                    <th>Type</th>
                                    <th>Size</th>
                                    <th>Price</th>
                                </tr>
                            </thead>
                            <tbody>
                                <div id="money">
                                    
                                </div>
                            </tbody>
                        </table>
                    
                        </div>
                    </div>
                    
                </div>
            </div>
        </div>
        ```
        OK, the framework of the web page has been completed.
        Then, write the javascript file to calculate the price and show the elements in a table.
        
        ```
        <script>
            function shoetype() {
                    return $("input:radio[name='shoetype']").is(":checked") && $("input:radio[name='size']").is(":checked");
                }
                
                function shoetypeprice() {
                    ShoeType = $("input[name='shoetype']:checked").val();
                    ShoeSize = $("input[name='size']:checked").val();
                    return ShoeType * ShoeSize;
                }
             function priceTotal() {
                    var total = 0;
                    total += shoetypeprice();
                    
                    
                }
            
            function tablerow(){
                var shoesID = $("input[name='shoetype']:checked").attr('id');
                    var sizeID = $("input[name='size']:checked").attr('id');
                    
                    var shoesLabel = $("label[for='"+shoesID+"']").text();
                    var sizeLabel = $("label[for='"+sizeID+"']").text();
                    
                    var pricevalue = $("input[name='shoetype']:checked").val() * $("input[name='size']:checked").val();
                    
                    var price = [shoesLabel, sizeLabel, pricevalue];
                    
                    return price;
            }
             function table() {
                    var table11 = [];
                    
                    table11.push(tablerow());
                 var html = "";
                    $.each(table11,function(i,a){
                        html += "<tr>"
                        $.each(a, function(ind,arr){
                            html +="<td>"
                            html += table11[i][ind];
                            html +="</td>"
                        });
                        html += "</tr>"
                    });
                    $('#price > tbody').html(html);
                }
                 
                
            function pricecalculation(){
                    if(shoetype()){
                        priceTotal();
                        table();
                    }
                    return false;
                    
                }
            
        </script>
    
  </body>
</html>
```
## push to GitHub
Finally, merge the new branch and push the file
```
git push -u origin Hw2-feature
git merge HW2-feature
git push -u origin master

```

Next time, I will try to sort out my homework, let them into a sigle repository.

        
    
    
    
    
    
    
