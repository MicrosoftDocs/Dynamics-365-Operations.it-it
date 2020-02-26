## <a name="product-category-assignments-to-msdyn_productcategoryassignments"></a>Assegnazioni di categorie del prodotto per msdyn_productcategoryassignments

Questo modello sincronizza i dati tra le app Finance and Operations e Common Data Service.

Campo di Finance and Operations | Tipo di mappa | Altro campo di Dynamics 365 | Valore predefinito
---|---|---|---
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber | 
PRODUCTCATEGORYNAME | = | msdyn_productcategory.msdyn_name | 
PRODUCTCATEGORYHIERARCHYNAME | = | msdyn_productcategory.msdyn_hierarchy.msdyn_name | 
PRODUCTNUMBER | >> | msdyn_name | 
