# NMS Noise Monitoring System

## Architecture

WebSocket server that relies on following other services
* nmpi Raspberry PI server in combination with PCE 430 Class 1 Meter and Huawei e5577 mobile router streams data to NMS via websocket connection
* Azure Storage used to permanently store the streamed measurements into block blobs (1 per hour) as CSV data, tab separated

It drives client SPAs called NMC that prime the data window from the storage directly but also connect to NMS via websocket to get pushes for new data with lowest possible latency.
