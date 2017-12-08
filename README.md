# java-testing

## Junit

### expected
```java
@Test(expected= IndexOutOfBoundsException.class) public void empty() { 
    new ArrayList<Object>().get(0); 
}
```
## Hamcrest

### check if single element is in a collection

```java
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, hasItem("cd"));
assertThat(collection, not(hasItem("zz")));
```    
### check if multiple elements are in a collection

```java
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, hasItems("cd", "ef"));
```    
### check all elements in a collection

– with strict order

```java
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, contains("ab", "cd", "ef"));
```
– with any order

```java
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, containsInAnyOrder("cd", "ab", "ef"));
```    
### check if collection is empty

```java
List<String> collection = Lists.newArrayList();
assertThat(collection, empty());
```    
### check if array is empty

```java
String[] array = new String[] { "ab" };
assertThat(array, not(emptyArray()));
```
### check if Map is empty

```java
Map<String, String> collection = Maps.newHashMap();
assertThat(collection, equalTo(Collections.EMPTY_MAP));
```
### check size of a collection

```java
List<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, hasSize(3));
```    
### checking size of an iterable

```java
Iterable<String> collection = Lists.newArrayList("ab", "cd", "ef");
assertThat(collection, Matchers.<String> iterableWithSize(3));
```    
### check condition on every item

```java
List<Integer> collection = Lists.newArrayList(15, 20, 25, 30);
assertThat(collection, everyItem(greaterThan(10)));
```
## Mockito

## Spring 
```
@MockBean
```  
  
