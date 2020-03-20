---
description: '题目链接：https://leetcode-cn.com/problems/two-sum/'
---

# 两数之和

解法一，暴力枚举法：

```java
public int[] byEnumerate(int[] nums, int target){
    int[] index = new int[2];

    for (int i = 0; i < nums.length; i++) {
        for (int j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] == target){
                index[0] = i;
                index[1] = j;
                return index;
            }
        }
    }
    throw new IllegalArgumentException("No two sum solution");
}
```

解法二，哈希映射法：

```java
public int[] byHashMap(int[] nums, int target){
    Map<Integer, Integer> hashMap = new HashMap<>(nums.length);
    for (int i = 0; i < nums.length; i++) {
        Integer x = target - nums[i];

        if (hashMap.containsKey(x)){
            return new int[]{hashMap.get(x), i};
        }
        hashMap.put(nums[i], i);
    }
    throw new IllegalArgumentException("No two sum solution");
}
```



