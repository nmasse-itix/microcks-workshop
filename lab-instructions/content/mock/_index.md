+++
title = "Mock"
weight = 4
chapter = true
pre = "<b>4. </b>"
+++

### Chapter 4

# Mock

In the **Mock** phase, you will define meaningful payload examples of your APIs and try to refine your specifications with business expectations for common and edge cases. Those examples are then turned into a live mock that can be exposed to your first consumers. “Business expectations” entail everything that cannot be specified using a formal schema. An example could be that when querying items by status, all returned items must have the desired status. You could also think about mutually exclusive options or dependencies between fields: for example, if the field companyName is set, then the field accountType needs to be “enterprise.”
