public class tenantschedulable implements Schedulable

{

public void execute(Schedulablecontext sc)

    {

       list<Tenant__c>  ten = [SELECT Id, Status_of_Possession__c FROM Tenant__c ];

        list<Tenant__c> tenantstodelete = New List<Tenant__c>();

        

        for(Tenant__c te: ten)

        {

            if(te.Status_of_Possession__c == 'Closed')

            {

                tenantstodelete.add(te);

            }

        }

        Delete tenantstodelete;

    }        

}
