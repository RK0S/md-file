###  1.  
Какой из двух фрагментов кода не сработает и почему?
  
Фрагмент 1:
```	
	console.log( doubleNum(10) );

	let doubleNum = (num) => {
		let result = num * 2;
		return result;
	}
```  

Фрагмент 2:
```
	console.log( doubleNum(10) );

	function doubleNum(num) {
    		let result = num * 2;
		return result;
	}
```  

## Решение:

<b>Сработает только 2 фрагмент</b> кода, так как Function Expression (doubleNum в 1 фрагменте кода) инициализируется во время того, как основной поток кода дошел до нее, а Function Declaration (doubleNum в 2 фрагменте кода) инициализируется в первую очередь и может быть использована до того, как была объявлена.

### 2.  
Исправьте ошибку в фрагменте коде так, чтобы после компиляции в шаблоне не было лишних тегов:
```
	<template>
		<component-name
			v-for="i of count" 
			:key="i"
			v-if="i < 10" 
		/>
	</template>

	<script>
	export default {
		data() {
			return {
				count: 20;
			};
		},
	};
	</script>  
```  

## Решение:

```
	<template>
        <template
            v-for="i of count" 
			:key="i"
        >
		    <component-name
			    v-if="i < 10" 
		    />
        </template>
	</template>

	<script>
	export default {
		data() {
			return {
				count: 20
			};
		},
	};
	</script>  
```  

### 3.  
Есть массив некоторых строительных материалов, каждый элемент массива - объекты с ключами id и количества материала. Напишите функцию, которая будет возвращать oбьект в формате { "id":"count" }

```
   resources = [
			{
			   id: 1,
			   count: 13,
   			},
			{
			   id: 2,
			   count: 5,
   			}, 
			{
			   id: 3,
			   count: 24,
   			},
		      {
			   id: 4,
			   count: 101,
   			}, 
			{
			   id: 5,
			   count: 72,
   			}, 
			{
			   id: 6,
			   count: 64,
   			}, 
			{
			   id: 7,
			   count: 305,
   			}, 
			{
			   id: 8,
			   count: 67,
   			}, 
			{
			   id: 9,
			   count: 95,
   			}, 
			{
			   id: 10,
			   count: 21,
   			}, 
			{
			   id: 11,
			   count: 37,
   			},
		   ];
```  

## Решение:

```
// Первое решение 
function solution1(arr) {
    const res = {}
    for (let { id, count} of arr) {
        res[id] = count
    }
    return res
}

// Второе решение 
function solution2(arr) {
    return arr.reduce((total, item) => {
        total[item.id] = item.count
        return total
    }, {})
}
```
Ожидаемый результат: 

```
  {
				   1: 13,
				   2: 5,
				   3: 24,
				   4: 101,
				   5: 72,
				   6: 64,
				   7: 305,
				   8: 67,
				   9: 95,
				   10: 21,
				   11: 37,
			     }
```  
