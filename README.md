# Block Layout Schema
## Layout
![alt text](https://raw.githubusercontent.com/luongdinhkhanhvinh/RES-web-UI/master/layout-pattern-block-1.webp?raw=true)

## Schema
```

interface IChildNode {
     uuid: string;
     label?: string;
     name?: string;
     child?: IChildNode[];
     postision?: string[];
     childContent?: string[];
     styles?: string;
     props?: string[];
}

interface PartialNode extends IChildNode {
    id: string;
    primaryLabel?: string;
}

```


## Collections request

### Create new partial layout
```
    const payload: PartialNode;
    
    Request description ------------------------------------> 
    + Method: @POST 
    + Route: /api/partial/
    + Payload {
        ...payload
    }
    Commission description --------------------------------->
    + Create new initial layout commponent maybe reuse for the future
    + Help client and SEO management and customize, create landing so easy
    
    Action description ------------------------------------->
    + When user click button create then sys show modal or redirect to page editor blocks 
    + In this page user can choose position view and filter childnode unlike or add childnode with hoobies and styles of website in repository blocks
    + When user feel perfect. User can click button preview website before click button publish
    + When user get event publish sys get request Create new partial layout fills payload and submit to backend
    + Note: User can can't save now can save file by craff (data craff maybe save from client or on redis server with uuid and json data) ->>> (1. Publish , 2. Save craff)
```


### Uppdate partial layout by id
```
     const payload: PartialNode;
    
    Request description ------------------------------------> 
    + Method: @PATCH 
    + Route: /api/partial/{id}
    + Payload {
        ...payload
    }
    
    Commission description --------------------------------->
    + Help client and SEO management and customize, update landing so easy by id of patial
    
    Action description ------------------------------------->
    + Similar request create but instead create patial then it only edit and update orderby each field instead update all model
```


### Bonus request
 + Search partial by name or position.
 + Delete partial error or so bad and ugly.