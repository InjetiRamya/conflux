# conflux

//create a file
at=vars.get("AT");
officeID="${officeID}";
userId="${userId}";
villageId="${villageId}";

// if you want to log something to jmeter.log file

// Pass true if you want to append to existing file
// If you want to overwrite, then don't pass the second argument
f = new FileOutputStream("${CenterMeeetingPreclosureAccessToken}",true);
p = new PrintStream(f); 
this.interpreter.setOut(p); 
print(at + "," + officeID +","+ userId +","+ villageId);
f.close();
// fetch value srom db and storing 
f1=new File("${DisbursementclientCount}");

if(f1.exists())
	{
		f1.delete();
	}

f = new FileOutputStream("${DisbursementclientCount}");

clientCount1=vars.getObject("clientCount").get(0).get("count(id)") + "";
p = new PrintStream(f); 
		this.interpreter.setOut(p); 
		print(clientCount1);
f.close();

//collection shheet

import com.finflux.user.data.UserDataGen;

at=vars.get("AT");
userId="${userId1}";

//System.out.println(at);
//System.out.println(userId);

String csvFile = "${CenterMeeetingCenterView}";
String csvFile1 = "${CenterMeeetingCenterViewAccessToken}";

UserDataGen.readAndWriteTestData(csvFile, csvFile1, 0, 1, 2, 3, userId,at);
