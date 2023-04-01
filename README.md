# Entity-Framework
## Custmize Table Section
``` c#
Use To Add Specific Name Table
[Table("productCollections")]

Exclude Table Not Added To Database
[NotMapped]
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
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

# Select
``` c# 
var SelectAll = await _context.TableName.ToListAsync();
var SelectSpecific = await _context.TableName.Select(a => new {name=a.Name,discription=a.Description}).ToListAsync();
```
# Where Cluse
``` c#
var Select = await _context.TableName.Where(a => a.Name == "khalid" ).ToListAsync();
```
# Delete Row
``` c# 
     var items = _context.TableName.Find(IdElement);
     _context.TableName.Remove(items);
     _context.SaveChanges();
```

# Update Row
``` c#
     var items = _context.TableName.Find(IdElement);
     items.name="salma";
     _context.SaveChanges();
```
# Order By (Sort)
``` c#

```

