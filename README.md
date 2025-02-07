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
<br>

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

