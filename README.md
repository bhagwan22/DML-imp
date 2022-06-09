# DML-imp

## apex DML of changing owenr will not sent email notification to new owner to allow, we need to use Database.DMLOptions
    
    Database.DMLOptions dlo = new Database.DMLOptions();    
    dlo.EmailHeader.triggerAutoResponseEmail = true;
    dlo.EmailHeader.triggerOtherEmail = true;
    dlo.EmailHeader.triggerUserEmail = true;

    Case ca = new Case(subject='Plumbing Problems', contactid=c.id);
    database.insert(ca, dlo);
