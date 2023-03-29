# Entity-Framework
## Change Table Name 
``` c#
[Table("productCollections")]
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
}
```

## Exclude The Table Dont Added To Database
``` c#
[NotMapped]
public class Orders
{
    public int OrderId { get; set; }
    public string OrderName { get; set; }
}
```

# Custmize The Column Section
``` c#
public class Order
{
    //Add Special Column Name
    [Column("Name")]
    public int Id { get; set; }
    
    //Add Specific Type
    [Column(TypeName = "nvarchar(50)")]    
    public string Description { get; set; }
    
    //Add Defaukt Value 
    [DefaultValueSql("('Pending')")]
    public string Status { get; set; }
    
    //Exclude property Column From Database
    [NotMapped]
    public decimal Price { get; set; }
}
```
