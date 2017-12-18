# java-testing

## Junit

### Testing Exceptions 

```java
@Test(expected= IndexOutOfBoundsException.class) public void empty() { 
    new ArrayList<Object>().get(0); 
}
```
### Parameterized Test
Define this on top of the class 
```java
@RunWith(value = Parameterized.class)
```
#### Parameterized via Constructor
```java
//default value = 0
    @Parameter(value = 0)
    public int numberA;
    
      @Parameters(name = "{index}: testAdd({0}+{1}) = {2}")//name is optional
    public static Collection<Object[]> data() {
        return Arrays.asList(new Object[][]{
                {1, 1, 2},
                {2, 2, 4},
                {8, 2, 10},
                {4, 5, 9},
                {5, 5, 10}
        });
    }

    @Test
    public void test_addTwoNumbes() {
        assertThat(MathUtils.add(numberA, numberB), is(expected));
    }
 ```
#### Parameterized via Field Injection
```java

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
```
@Mock
```  

```
@Spy
```  

```
@Spy
```  
## Spring 
```
@MockBean
```  
```
@SpyBean
```  
  
