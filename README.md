Run example:

```
ansible-galaxy install geerlingguy.java
ansible-galaxy install geerlingguy.postgresql
cd examples/digipoort
ansible-playbook playbook.yml --ask-become-pass
cd examples/demo/overheid
ansible-playbook playbook.yml --ask-become-pass
```

open http://localhost:8080/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.cpa.CPAsPage in your browser and upload cpa examples/cpa.xml  
open http://localhost:8000/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.cpa.CPAsPage in your browser and upload cpa examples/cpa.xml

- next from the digipoort console you can:
	- execute a ping the overheid adapter at http://localhost:8080/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.message.PingPage
		- CPA Id:     cpaStubEBF.rm.https.signed
		- From Party: urn:osb:oin:00000000000000000000
		- To Party:   urn:osb:oin:00000000000000000001
	- send a message to the overheid adapter at http://localhost:8080/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.message.SendMessagePageX
		- CPA Id:        cpaStubEBF.rm.https.signed
		- From Party Id: urn:osb:oin:00000000000000000000
		- Service:       urn:osb:services:osb:afleveren:1.1$1.0
		- Action:        afleveren
	- view traffic at http://localhost:8080/wicket/bookmarkable/nl.clockwork.ebms.admin.web.message.TrafficPage

- next from the overheid console you can:
	- execute a ping the digipoort adapter at http://localhost:8000/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.message.PingPage
		- CPA Id:     cpaStubEBF.rm.https.signed
		- From Party: urn:osb:oin:00000000000000000001
		- To Party:   urn:osb:oin:00000000000000000000
	- send a message to the digipoort adapter at http://localhost:8000/wicket/bookmarkable/nl.clockwork.ebms.admin.web.service.message.SendMessagePageX
		- CPA Id:        cpaStubEBF.rm.https.signed
		- From Party Id: urn:osb:oin:00000000000000000001
		- Service:       urn:osb:services:osb:aanleveren:1.1$1.0
		- Action:        aanleveren
	- view traffic at http://localhost:8000/wicket/bookmarkable/nl.clockwork.ebms.admin.web.message.TrafficPage
