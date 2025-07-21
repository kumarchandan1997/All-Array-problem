# Important Array Questions with Answer

### 1. Reverse an array without using built-in functions.

```php
$array = [1,2,3,4,5];
    // print_r(array_reverse($array));
    
    function reverseArray($array)
    {
    
    $length = 0;
    $reverse = '';
    while(isset($array[$length])){
        $length++;
    }
    
    for($i=$length-1;$i>=0;$i--)
    {
        $reverse .= $array[$i];
    }
    return $reverse;
    }
    print_r(reverseArray($array));
```
<!-- <br> -->

### 2. Find the largest and smallest numbers in an array.

```php
  $array = [-1,-2,-3000000,-40000,50000];
    
    function findMaxAndMin($array)
    {
        $max = $array[0];
        $min = $array[0];
        $length =0;
        while(isset($array[$length])){
            $length++;
        }
        
        for($i =0;$i<$length;$i++)
        {
            if($array[$i]>$max)
            {
                $max = $array[$i];
            }
            
            if($array[$i]<$min)
            {
                $min = $array[$i];
            }
        }
        return ['max' => $max ,'min'=> $min];
    }
    
    print_r(findMaxAndMin($array));
```

### 3.Remove duplicate elements from an array.

```php
  $array = [1,2,3,4,1,4,2,3,4,19];
    
    function removeDublicate($array)
    {
        $length=0;
        $newArray = [];
        $seen = [];
        
        while(isset($array[$length])){
            $length++;
        }
        
        for($i=0;$i<$length;$i++)
        {
            if(!isset($seen[$array[$i]])){
                $newArray[] = $array[$i];
                $seen[$array[$i]] = true;
            }
        }
        return $newArray;
    }
    print_r(removeDublicate($array));

    $array = [1,2,3,4,3,2,1,4,89,90,90];
    $duplicate=[];
    foreach($array as $arr)
    {
        $duplicate[$arr] = $arr;
    }
    print_r(array_values($duplicate));

```

### 4.Merge two arrays without using array_merge().
```php
    $array1 = [1,2,3,4];
   $array2 = [2,3,4];
   //print_r(array_merge($array1,$array2));
   function mergeArray($array1,$array2)
   {
    $length1 = 0;
    $length2 = 0;
    
    while(isset($array1[$length1])){
        $length1++;
    }
    
    while(isset($array2[$length2])){
        $length2++;
    }
    
    for($i=0;$i<$length2;$i++)
    {
        $array1[$length1+$i] = $array2[$i];
    }
    return $array1;
   }
   
   print_r(mergeArray($array1,$array2));

    $fruits = ["mongo"=>12,'banana'=>123,'juice'=>'1234']; 
    $vegetables = ["pototo"=>12,'loki'=>1234];
     // print_r(array_merge($fruits,$vegetables));
    foreach($vegetables as $key =>$value)
    {
    $fruits[$key] = $value;
   }
   print_r($fruits);

```

### 5.Find the second largest number in an array.

```php
  $array = [5, 2, 8, 1, -9];
  //sort($array);

  function bubbleSort($arr)
  {
      $n = 0;
      while(isset($arr[$n]))
      {
          $n++;
      }
      
      for($i=0;$i<$n;$i++)
      {
          for($j=0;$j<$n-$i-1;$j++)
          {
              if($arr[$j] > $arr[$j+1]){
                  $temp = $arr[$j];
                  $arr[$j] = $arr[$j+1];
                  $arr[$j+1] = $temp;
              }
          }
      }
      return $arr;
  }

  print_r(bubbleSort($array));
  ```

  ### 6.Find the sum of all elements in an array.

  ```php
   $array = [5, 2, 8, 1, -9];
  
  function sumOfArray($arr)
  {
      $sum =0;
      $n = 0;
      while(isset($arr[$n])){
          $n++;
      }
      
      for($i=0;$i<$n;$i++)
      {
          $sum = $sum +$arr[$i];
      }
      return $sum;
  }
  echo sumOfArray($array);
  ```

  ### 7.Sort an array without using sort().

  ```php
   $array = [5, 2, 8, 1, 9];
    //sort($array);

  function bubbleSort($arr)
  {
      $n = 0;
      while(isset($arr[$n]))
      {
          $n++;
      }
      
      for($i=0;$i<$n;$i++)
      {
          for($j=0;$j<$n-$i-1;$j++)
          {
              if($arr[$j] < $arr[$j+1]){
                  $temp = $arr[$j];
                  $arr[$j] = $arr[$j+1];
                  $arr[$j+1] = $temp;
              }
          }
      }
      return $arr;
  }

  print_r(bubbleSort($array));

  ```

  ### 8.Check if a given value exists in an array (in_array() alternative).
  ```php
    $array = [5, 2, 8, 1, 9];
    $value = 50;

    function checkValueInArray($arr,$value)
    {
        //return in_array($value,$arr);
        $n = count($arr);
        for($i=0;$i<$n;$i++)
        {
            if($arr[$i] == $value)
            {
                return true;
                break;
            }
        }
        return false;
    }

    if((checkValueInArray($array,$value))){
        echo "yes present";
    }else{
        echo "not present";
    }

  ```
  ### 9.Count occurrences of each element in an array.
  ```php
   $array = [5, 2, 8, 1, 9,1,2,3,4];
  
   function occurrenceOfElement($arr)
   {
       $newArray = [];
       
       for($i=0;$i<count($arr);$i++)
       {
           if(isset($newArray[$arr[$i]])){
               $newArray[$arr[$i]]++;
           }else{
               $newArray[$arr[$i]] = 1; 
           }
       }
       return $newArray;
   }
   print_r(occurrenceOfElement($array));
  ```

  ### 10.Find common elements between two arrays.
  ```php
   $array = [1,2,3,4];
   $array1 = [1,3,4,4];
  
   function findCommonData($arr,$arr1)
   {
       $newArray = [];
      
      for($i=0;$i<count($arr);$i++)
      {
          for($j=0;$j<count($arr1);$j++)
          {
              if($arr[$i] == $arr1[$j]){
                  if(!in_array($arr[$i] ,$newArray)){
                       $newArray[] = $arr[$i];
                  }
                 
              }
          }
      }
      return $newArray;
      
   }
   print_r(findCommonData($array,$array1));
  ```

  ### 11.Find the most frequently occurring element in an array.
  ```php
  function findMostFrequently($array)
   {
       $newArray=[];
       $length=0;
       while(isset($array[$length])){
           $length++;
       }
       for($i=0;$i<$length;$i++)
       {
           if(isset($newArray[$array[$i]])){
               $newArray[$array[$i]]++;
           }else{
               $newArray[$array[$i]] =1;
           }
       }
       
       $mostFrequent = null;
       $maxCount = 0;
    
    foreach ($newArray as $key => $count) {
        if ($count > $maxCount) {
            $maxCount = $count;
            $mostFrequent = $key;
        }
    }
    
    return $mostFrequent;
   }
   
   $array = [1,2,2,2,2,3,3,4];
   
  print_r(findMostFrequently($array));
   
  ```
  ### 12.Implement array_map() functionality manually.
  ```php
   $array = [1, 2, 3, 4, 6];

   function manularrayMap($callback,$arr)
   {
       $result =[];
       
       foreach($arr as $key => $value)
       {
           $result[$key] = $callback($value);
       }
       return $result;
   }
   
   function multipleNumber($num)
   {
       return $num *2;
   }
   print_r(manularrayMap('multipleNumber',$array));
   ```

 ### 13.Find the intersection and difference of two arrays without built-in functions.
 ```php
  $array = [1, 2, 3];
  $array1 = [1,4,3]; 
  
  //print_r(array_intersect($array,$array1));

  function intersectOfArray($arr,$arr1)
  {
      $result =[];
      
      for($i=0;$i<count($arr);$i++)
      {
          for($j=0;$j<count($arr1);$j++)
          {
              if($arr[$i] === $arr1[$j]){
                    $result[] = $arr[$i];
                    break;
              }
          }
      }
      return ($result);
  }
  
  print_r(intersectOfArray($array,$array1));

 ```

 ### 14.Find the missing number in an array of consecutive numbers.
 ```php
  $array = [1,2,3,4,6];
  
   function consecutiveMissingNumber($arr)
   {
       $finalNumber = 0;
       $arraySum = array_sum($arr);
       $n = count($arr)+1;
       $mathSum = ($n *($n+1))/2;
       $finalNumber = ($mathSum) - ($arraySum);
       return $finalNumber;
   }
   
   echo consecutiveMissingNumber($array);
 ```

 ### 15.Rearrange an array so that even numbers come before odd numbers.
 ```php
 $array = [1, 2, 3,4,5,6];
  
   function rearrangeArray($arr)
   {
       $evenNumber = array_filter($arr, function($num){
           return $num%2 ==0;
       });
       
       $oddNumber = array_filter($arr , function($num){
           return $num %2 != 0;
       });
       
       return array_merge($evenNumber,$oddNumber);
   }
   
   print_r(rearrangeArray($array));

   $array = [1, 2, 3,4,5,6];
  
   function rearrangeArray($arr)
   {
       $evenArray = [];
       $oddArray = [];
       
       foreach($arr as $ar)
       {
           if($ar %2 ==0)
           {
               $evenArray[] =$ar;
           }else{
               $oddArray[] = $ar;
           }
       }
       $result =[];
       
       foreach($evenArray as $even)
       {
           $result[] =$even;
       }
       foreach($oddArray as $odd)
       {
           $result[] =$odd;
       }
       return $result;
   }
   
   print_r(rearrangeArray($array));
   ```

   ### 15.Rotate an array by n positions.
   ```php
    function rotateArrayRight($arr, $n) {
    $length = count($arr);
    $n = $n % $length;

    if ($n == 0) return $arr;

    return array_merge(array_slice($arr, -$n), array_slice($arr, 0, $length - $n));
  }

    $arr = [1, 2, 3, 4, 5, 6, 7];
    $n = 2;

    $result = rotateArrayRight($arr, $n);
    print_r($result);

    #second and best approch

    function leftRotation($arr,$d)
    {
        $n = count($arr);
        $d=$d % $n;
        $temp = array_slice($arr,0,$d);
        
        for($i=0;$i<$n-$d;$i++)
        {
            $arr[$i]=$arr[$d+$i];
        }
        
        for($j=0;$j<$d;$j++)
        {
            $arr[$n-$d+$j] = $temp[$j];
        }
        
        return $arr;
    }

   ```

   ### 16.Find all pairs in an array that sum up to a given number.

   ```php
   function findPairsWithSum($arr,$value)
   {
    $seen =[];
    $pair =[];
    
    foreach($arr as $num)
    {
        $complement = $value-$num;
        if(isset($seen[$complement])){
            $pair[] =[$complement,$num];
        }
        $seen[$num] =true;
    }
    return $pair;
   }
    $array = [1, 4, 6, 2, 3, 7, 8, 5];
    $target = 5;
    print_r(findPairsWithSum($array,$target));
 ```

 ### 17.Convert an associative array into JSON and back to an array.
 ```php
    $assocArray = [
    "name" => "John Doe",
    "age" => 30,
    "email" => "john@example.com",
    "skills" => ["PHP", "JavaScript", "Laravel"]
    ];

    $jsonString = json_encode($assocArray, JSON_PRETTY_PRINT);
    echo "JSON String:\n" . $jsonString . "\n\n";


    $decodedArray = json_decode($jsonString,true);
    print_r($decodedArray);
```

 ### 18.Implement a stack and queue using PHP arrays.
 ```php
  class stack{
      private $stack =[];
      
      public function push($element)
      {
          array_push($this->stack,$element);
      }
      
      public function pop(){
          if(!$this->isEmpty()){
              return array_pop($this->stack);
          }
          return null;
      }
      public function peek(){
          return !$this->isEmpty() ? end($this->stack) :null;
      }
      public function isEmpty(){
          return empty($this->stack);
      }
      public function display(){
          print_r(array_reverse($this->stack));
      }
  }
    $stack = new Stack();
    $stack->push(10);
    $stack->push(20);
    $stack->push(30);

    echo "Stack after pushing elements:\n";
    $stack->display();

    echo "\nPopped element: " . $stack->pop() . "\n";
    echo "Stack after popping:\n";
    $stack->display();
```

### 19.Find all vowels from given array? 
```php
    $array = ["chandan kumar"];
    $vowels = ['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'];
    $result = [];

    foreach ($array as $word) {
        $length = 0;
        while (isset($word[$length])) { 
            $length++;
        }

        for ($i = 0; $i < $length; $i++) {
            foreach ($vowels as $vowel) {
                if ($word[$i] == $vowel) {
                    $result[] = $word[$i];
                    break;
                }
            }
        }
    }

    print_r($result);

```

 ### 20.Remove a key-value pair from an associative array.
```php
  $fruits = ["mongo"=>12,'banana'=>123,'juice'=>'1234'];

    //unset($fruits['banana']);
   //print_r($fruits);

  $newArray =[];
  
  foreach($fruits as $key => $value)
  {
      if($key !== 'mongo')
      {
          $newArray[$key] =$value;
      }
  }
  print_r($newArray);
  ```
### 21.Reverse words only without use of in-build function in php
```php
  $string = "my name is chandan kumar yadav";
  
  function reverseString($string)
  {
      $words = explode(" ",$string);
      $length=0;
        $newArray = [];
      while(isset($words[$length])){
          $length++;
      }
 
    
      for($i=$length-1;$i>=0;$i--)
      {
          $newArray[] = $words[$i];
      }
      return implode(" ",$newArray);
  }
  print_r(reverseString($string));
  ```

### 22.Two sum problem in leetcode
```php
  function twoSum($nums , $target)
 {
    $map =[];
    foreach($nums as $index => $num){
        $complement = $target-$num;
        
        if(isset($map[$complement]))
        {
            return [$map[$complement],$index];
        }
        
        $map[$num] =$index;
    }
    return null;
}
$nums = [2, 7, 11, 15];
$target = 17;

$result = twoSum($nums, $target);
print_r($result);
  ```

### 23.Remove Element array from leet code
```php
  function removeElement(&$nums, $val) {
    $n = count($nums);
    $i = 0;
    for ($j = 0; $j < $n; $j++) {
        if ($nums[$j] !== $val) {
            $nums[$i] = $nums[$j];
            $i++;
        }
    }
    
    for ($k = $i; $k < $n; $k++) {
        $nums[$k] = '_';
    }
    
    return $nums;
}
$nums = [3, 2, 2, 3];
$val = 3;

$newLength = removeElement($nums, $val);

print_r($nums);
  ```

### 24.Search insert position and if not find than insert position from leet code
```php
 function searchInsert($nums, $target) {
        $n = count($nums);

        for($i=0;$i<$n;$i++)
        {
            if($nums[$i] == $target){
                return $i;
            }
        }

        for($j=0;$j<$n;$j++)
        {
            if($target<$nums[$j]){
                return $j;
            }
        }
        return $n;
    }
}

second  approch by use of binary search

function findIndex($nums, $target) {
    $left = 0;
    $right = count($nums) - 1;
    
    while ($left <= $right) {
        $mid = $left + (int)(($right - $left) / 2);
        
        if ($nums[$mid] == $target) {
            return $mid;
        } elseif ($nums[$mid] < $target) {
            $left = $mid + 1;
        } else {
            $right = $mid - 1;
        }
    }
    
    return $left;
}
  ```
### 25.Plus one in last of array in leetcode
```php
  function plusOne($digits) {
        $n = count($digits);
    
    
    for ($i = $n - 1; $i >= 0; $i--) {
        if ($digits[$i] < 9) {
            $digits[$i]++;
            return $digits;
        }
        
        $digits[$i] = 0;
    }
    
    array_unshift($digits, 1);
    return $digits;
    }
  ```

### 26.Sum of good numbers in leetcode
```php
  function sumOfGoodNumbers($nums, $k) {

       $sum = 0;
       $n = count($nums);

        for ($i = 0; $i < $n; $i++) {
            $isGood = true;

            // Check the element at index i - k, if it exists
            if ($i - $k >= 0 && $nums[$i] <= $nums[$i - $k]) {
                $isGood = false;
            }

            // Check the element at index i + k, if it exists
            if ($i + $k < $n && $nums[$i] <= $nums[$i + $k]) {
                $isGood = false;
            }

            // If the current element is good, add it to the sum
            if ($isGood) {
                $sum += $nums[$i];
            }
        }

    return $sum;
    }
  ```

### 27. Find single number from array in leetcode
```php
  function singleNumber($nums) {
        $newArray =[];
        foreach($nums as $value)
        {
            if(isset($newArray[$value]))
            {
                $newArray[$value]++;
            }else{
                $newArray[$value]=1;
            }
        }
        foreach($newArray as $key => $value)
        {
            if($newArray[$key] ==1)
            {
                return $key;
            }
        }
        
    }

# second approch

$array = [1,2,3,3,2,1,4];

  function singleNUmber($array)
  {
      $result=0;
      foreach($array as $value)
      {
          echo $result."\n";
          $result ^=$value;
      }
      return $result;
  }
  echo singleNUmber($array);
  ```

### 28.Stock buy and sell on max profit in leetcode
```php
  function maxProfit($prices) {
        $minPrice = PHP_INT_MAX;
        $profit=0;

        foreach($prices as $value)
        {
            if($value<$minPrice)
            {
                $minPrice = $value;
            }elseif($value-$minPrice>$profit)
            {
                $profit=$value-$minPrice;
            }
        }
        return $profit;
    }

#second approch

 function bestTimeToBuyStock($array)
  {
      $n=count($array);
      $profit=0;
      
      for($i=0;$i<$n;$i++)
      {
          for($j=$i+1;$j<$n;$j++)
          {
              if($array[$j]-$array[$i] >$profit)
              {
                  $profit = $array[$j]-$array[$i];
              }
          }
      }
      return $profit;
  }
  
  echo bestTimeToBuyStock($array);
  ```
### 29.Right shift rotation
```php
$arr = [1, 2, 3, 4, 5, -5, 6, -6]; //8
$shift = 20;

  function arrayRightShift($arr,$shift)
  {
      $length=0;
      while(isset($arr[$length])){
          $length++;
      }
      
      if($length<$shift){
          return "Shift size must be less than or equal to array length !";
      }
      
      if($length == $shift){
          return $arr;
      }
      
      $result = [];
      
      for($i=$length-$shift;$i<$length;$i++){
          $result[]=$arr[$i];
      }
      
      for($i=0;$i<$length-$shift;$i++){
          $result[]=$arr[$i];
      }
      return $result;
  }
  print_r(arrayRightShift($arr, $shift));

```
### 30.Left shift rotation
```php
$arr = [1, 2, 3, 4, 5,6];
$shift = 10;

function arrayLeftShift($arr, $shift)
{
    $length=0;
    while(isset($arr[$length])){
        $length++;
    }
    
    if($shift > $length){
        return "Shift length must be equal or less than array length !";
    }
    
    if($shift == 0 || $shift == $length){
        return $arr;
    }
    
    $result =[];
    
    for($i=$shift;$i<$length;$i++)
    {
        $result[]=$arr[$i];
    }
    
    for($i=0;$i<$shift;$i++){
        $result[]=$arr[$i];
    }
    return $result;
}

print_r(arrayLeftShift($arr, $shift));

```
### 31.Check if an array is a palindrome (same forward and backward).
```php
$arr3 = ['a', 'b', 'b', 'a'];
  
  
  function checkPalindromeArray($arr){
  $n=count($arr);
  for($i=0;$i<$n/2;$i++)
  {
      if($arr[$i] !== $arr[$n-$i-1]){
        return false;   
      }
      return true;
  }
  }
echo checkPalindromeArray($arr3) ? "Palindrome\n" : "Not Palindrome\n";
  




