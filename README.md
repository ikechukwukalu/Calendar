# Calendar
Get all dates and their corresponding days using php

```
$year = strftime("%Y", time());
$month = ['01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12'];
$list = [];

foreach($month as $m) {
    $nDays = cal_days_in_month( 0, $m, $year);
    $dates = [];

    for($d = 1; $d <= $nDays; $d ++)
    {
        $time = mktime($m, 0, 0, $m, $d, $year);          
        if (date('m', $time) == $m) {
            $dates[] = date('Y-m-d-D', $time);
        }
    }
    $list[] = $dates;

}
echo "<pre>";
print_r($list);
echo "</pre>";
```
