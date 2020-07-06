# Test Task for MindConnect
## Task 1
```
class test1{
    //function to get last word in sentence
    Static function last_word($sentence){
        if (is_string($sentence) && $sentence != ""){
            $words = explode(' ', $sentence);
            $last = array_pop($words);
            return $last;
        }else { return 0; }
    }
     
    //function to make sql date format from simple date
    Static function sql_date_format($dateStr){
        $sqldate = date('Y-m-d', strtotime($dateStr));
        return $sqldate;
    }

    //function to extract part of the string in squere parentheses
    Static function extract_string($str){
        preg_match_all('#\[([\d\w\s]+)\]#', $str, $match);
        if ($match[1][0]){
            return $match[1][0];
        }else { return ""; }
    }
}
```
## Task 2
```
class test2{
        //function for checking the integer power of two numbers
        Static function is_power($number,$base){
            $power = pow($number, 1/$base);
            if ($power - (int)$power == 0){
                return true;
            }else { return false; }
        }
        //function to delete all characters except numbers, dots and commas
        Static function format_number($str){
            preg_match_all("/[0-9.,]+/", $str, $matches);
            return implode('', $matches[0]);
        }
        //function to sum all digits from integer
        Static function sum_digits($int){
            $int = strval($int);
            $sum = 0;
            for ($i = 0; $i < strlen($int); $i++){
                $sum += $int[$i];
            }
            return $sum;
        }
}
```
## Task 3
The code will not work obviously, as the strpos function will return 0, and "if" statement will not work correctly, so you need to use type checking. The following code will work correctly
```
$str1 = 'yabadabadoo';
$str2 = 'yaba';
if (strpos($str1, $str2) !== false) {
  echo "\"" . $str1 . "\" contains \"" . $str2 . "\"";
}else {
  echo "\"" . $str1 . "\" does not contain \"" . $str2 . "\"";
}
```
## Task 4
The query will return three fields with one "Null" value, because it uses "Left Join" and "Moshe" from table "a" don't have the corresponding value from table "b"
## Task 5
Function "Now()" will return current date and time in format "dd/mm/YYYY hh:mm::ss", when function "current_date()" will return only date without time in format "dd/mm/YYYY".
## Task 6
The "Union" operation is used to combine the results of two queries, where the number of columns must match and they must have data types that are compatible. This operation is used when it is necessary to perform one query with different parameters, but it is impossible to perform with one condition.
## Task 7
1. Write an SQL statement to get all customers' name, city and salesmans' names, which the salesman's commission is between 12% and 14%.
```
SELECT customer.Name, customer.city, salesman.Name 
FROM customer, salesman 
WHERE salesman.Id = customer.Salesman_id AND salesman.commision > 0.12 AND salesman.commision < 0.14
```
2. Write an SQL statement to get all salesmen that didn't sell anything.
```
SELECT salesman.* 
from salesman 
WHERE NOT EXISTS (select customer.Id FROM customer WHERE customer.Salesman_id = Salesman.Id)
```
## Task 8
Function that removes duplicates of an array and return an array of only unique elements.
```
var arr = [1, 2, 3, 5, 1, 5, 9, 1, 2, 8];
function unique (arr){
	var arru = [];
  for (var i=0; i < arr.length; i++){
  	if(arru.includes(arr[i]) == false){
    	arru.push(arr[i]);
    }
  }
};
unique(arr);//[1, 2, 3, 5, 9, 8]
```
## Task 9
Function that duplicates array n-times.
```
function duplicate (arr, times){
	var arr_res = [];
  for (var i=0; i < times; i++){
  	arr_res = arr_res.concat(arr);
  }
  return arr_res;
};

console.log(duplicate([1, 2, 3, 4, 5], 3)); // [1,2,3,4,5,1,2,3,4,5,1,2,3,4,5]
```
## Task 10
The problem is that the function binding is only for existing elements. This can be fixed with the "on ()" function on the parent element and with the selector parameter on those elements to be added. The working code is below.
```
$('body').on('click', 'button', function() {
 	console.log( "Button Clicked:", this);
});

/* ... some time later ... */
// dynamically add another button to the page
$( "body" ).append( "<button class='btn'>Click Alert!</button>" );
```
## Task 11
HTML:
```
<html>
  <head>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
  </head>
  <body>
    <button type="button" class="btn btn-primary my_btn">
      +1 <span class="badge badge-light my_span">0</span>
    </button>
  </body>
</html>
```
JS:
```
$(".my_btn").on("click", function(){
	var i = $(".my_span").text();
  i++;
  $(".my_span").text(i);
});
```
