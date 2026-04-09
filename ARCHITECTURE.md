# Architecture Documentation

## Workflow Overview  
This document provides an overview of the architecture and data flow within the system.

## Flow Diagram  
![Flow Diagram](link_to_flow_diagram)

## Detailed Explanation of Each Node  
1. **Webhook Receiver**  
   - This node listens for incoming webhooks from external sources and validates the requests.
   
2. **Event Parser**  
   - Extracts relevant data from the received webhooks and formats it for processing.
   
3. **Site Searcher**  
   - This component searches the site database for relevant information related to the event.
   
4. **Wired Client Searcher**  
   - Identifies wired clients connected to the network based on the event's payload.
   
5. **Port Deduplicator**  
   - Ensures that there are no duplicate entries for ports in the data stream.
   
6. **Device Resolver**  
   - Maps the identified clients to their respective device types and details.
   
7. **Port Disabler**  
   - Disables the specified ports based on the provided criteria and configurations.
   
8. **Email Builder**  
   - Constructs email notifications to inform users of actions taken or issues encountered.

## Data Flow Between Nodes  
The data flows sequentially through the above nodes as follows:  
1. Webhook Receiver → 2. Event Parser → 3. Site Searcher → 4. Wired Client Searcher → 5. Port Deduplicator → 6. Device Resolver → 7. Port Disabler → 8. Email Builder.

## Error Handling and Skip Logic  
Each node includes error handling mechanisms to skip processing for invalid data or failed operations while logging errors for review.

## API Endpoints Used  
- **GET /api/site** - Retrieves site information.  
- **POST /api/device** - Updates device states.

## Payload Structures  
### Incoming Webhook Payload  
```json
{
  "type": "event_type",
  "data": {
    "siteId": "1234",
    "clientId": "abcd"
  }
}
```

### Email Payload  
```json
{
  "to": "user@example.com",
  "subject": "Notification",
  "body": "Details about the operation." 
}
```

## Security Considerations  
- Validate all incoming data to prevent injection attacks.  
- Use HTTPS for all API endpoints to secure data in transit.  
- Implement rate limiting on the webhook receiver to mitigate DDoS attacks.