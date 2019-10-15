This file describes remote-run REST API

 /**
   @apiDefine nodeId

   @apiParam (URL parameters) {UUID} id ID of the node.
*/

 /**
   @apiDefine nodeIds

   @apiParam {UUIDs} ids Comma-separated list of node IDs
*/

/**
   @apiDefine keepOutput

   @apiParam {Boolean} [keep_output=false] Forward agent output
*/

/**
   @apiDefine asynchronous

   @apiParam {Boolean} [asynchronous=false] Return early or wait for the end of the agent run
*/

/**
   @apiDefine conditions

   @apiParam {Conditions} [conditions] Conditions passed as parameter to make it available during agent run, separated by a comma, each condition must match `^[a-zA-Z0-9][a-zA-Z0-9_]*$`
*/

/**
   @apiDefine classes

   @apiParam {Conditions} [classes] Deprecated alias for `classes`
*/

== [POST] api/remote-run/nodes/{id}

    /**
    @api {post} /api/remote-run/nodes/{id} 1. Trigger a run on a specific node
    @apiVersion 1.0.0
    @apiName remoteRunNode
    @apiGroup Remote run
    
    @apiUse nodeId
    @apiUse conditions
    @apiUse classes
    @apiUse keepOutput
    @apiUse asynchronous

    @apiExample Example usage:
    curl http://localhost:3030/rudder/api/1/remote-run/nodes/2fc7a3a2-4050-4209-afe9-1c5ebc9ce2c8
  
     */

== [POST] api/remote-run/nodes

    /**
    @api {post} /api/remote-run/nodes 2. Trigger a run on a list of nodes
    @apiVersion 1.0.0
    @apiName remoteRunNodes
    @apiGroup Remote run
    
    @apiUse nodeIds
    @apiUse conditions
    @apiUse classes
    @apiUse keepOutput
    @apiUse asynchronous

    @apiExample Example usage:
    curl http://localhost:3030/rudder/api/1/remote-run/nodes
  
     */

== [POST] api/remote-run/nodes/all

    /**
    @api {post} /api/remote-run/nodes/all 3. Trigger a run on a all nodes managed by target relay
    @apiVersion 1.0.0
    @apiName remoteRunNodeAll
    @apiGroup Remote run
    
    @apiUse conditions
    @apiUse classes
    @apiUse keepOutput
    @apiUse asynchronous

    @apiExample Example usage:
    curl http://localhost:3030/rudder/api/1/remote-run/all
  
     */