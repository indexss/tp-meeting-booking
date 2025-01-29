> Last Updated: 01/29/2025

<div style="color: red;">

**If you have any questions and need to email me, you're welcome, but please include your group number in the email subject. This will help me quickly understand the context.**

</div>

### Before the first meeting with TA
- It would be best to meet and get to know each other in advance.
- Create online groups.
- It would be best if the group could coordinate the project topics well. If not, at least each team member should come up with some of their own so that we can dive directly into the discussion.

### Common Questions

**Q: How to arrange future meetings?**

A: Note that the module requires you to hold at least two meetings per week—one with the TA and one without. 
For the meeting with the TA, you need to use this website each week to book my meeting time slot. Ideally, my time slots are fixed: I have some in-person meeting time slots on Wednesdays and some Zoom meeting time slots on Fridays. However, I cannot guarantee that these will remain unchanged, so I only open the booking window for the next seven days. 
Additionally, if you are unable to coordinate your schedules within the given time slots, you can email me to arrange a new time.

**Q: My team member never communicates with the rest of us, and we don't know him. What should we do?**

A: Seed an e-mail to me with the name of the team member.

**Q: Can you provide an example of a JDL?**

A: The most official JDL examples have been provided in the [masterclass documentation](https://canvas.bham.ac.uk/courses/78925/files/18281380?module_item_id=4126397). But I can also show you my example:

```java
entity VendingMachine {
  id Long,
  name String required,            
  inventory Integer,             
  balance BigDecimal,              
  manufactureDate Instant        
}

entity Product {
  id Long,
  name String required,           
  category String,                
  price BigDecimal required,        
  manufactureDate Instant,          
  expirationDate Instant            
}

relationship ManyToMany {
  VendingMachine{products} to Product{vendingMachines}
}

//generate data transfer object, Help you decouple the actual operational objects of Spring Boot from the database objects.
dto VendingMachine, Product with mapstruct 

// generate service layer code automatically.
service VendingMachine, Product with serviceClass

// enable paginate query for Commodity
paginate Product with pagination
```

