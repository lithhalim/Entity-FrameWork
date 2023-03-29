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
    //Add Primery Key
    [Key]
    public int OrderId { get; set; }
    
    //Add Special Column Name
    [Column("Name")]
    public String OrderName { get; set; }
    
    //Add Specific Type
    [Column(TypeName = "nvarchar(50)")]    
    public string Description { get; set; }
    
    //Add Default Value 
    [DefaultValueSql("('Pending')")]
    public string Status { get; set; }
    
    //Exclude property Column From Database
    [NotMapped]
    public decimal Price { get; set; }
    
    //Add Macimum Length 
    [StringLength(50)]
    public string Email { get; set; }
    


}
```
