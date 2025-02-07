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
  ``php
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

