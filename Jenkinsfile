stages:
- prepare
- yesPleaseDo
- noDont
 
steps:
 step_1:
   image: alpine:3.8
   title: building chart
   stage: prepare
   commands:
   - echo "prepare"
 deployToProdNow:
   type: pending-approval
   title: Should we deploy to prod
   stage: prepare
 step_2:
   image: alpine:3.8
   title: prepare environment
   stage: yesPleaseDo
   commands:
   - echo "world"
   when:
     steps:
     - name: deployToProdNow
       on:
       - approved
 step_3:
   image: alpine:3.8
   title: deploy to production
   stage: yesPleaseDo
   commands:
   - echo "world"
   when:
     steps:
     - name: deployToProdNow
       on:
       - approved
 step_4:
   image: alpine:3.8
   title: prepare environment
   stage: noDont
   commands:
   - echo "world"
   when:
     steps:
     - name: deployToProdNow
       on:
       - denied
 step_5:
   image: alpine:3.8
   title: deploy to staging
   stage: noDont
   commands:
   - echo "world"
   when:
     steps:
     - name: deployToProdNow
       on:
       - denied +
