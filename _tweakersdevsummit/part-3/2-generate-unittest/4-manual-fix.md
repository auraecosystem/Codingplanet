Add the following to the test.
```java
@BeforeEach
public void setUp() {
    // Initialize the database schema and insert test data here if needed
    dslContext.insertInto(Customers.CUSTOMERS,
            Customers.CUSTOMERS.FIRST_NAME,
            Customers.CUSTOMERS.LAST_NAME)
            .values("Vince", "Doe")
            .execute();
}

@AfterEach
public void tearDown() {
    dslContext.truncateTable(CUSTOMERS).cascade().execute();
}
```

[Next](5-result-pitest.png)