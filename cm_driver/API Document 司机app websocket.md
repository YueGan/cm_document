### API Document 司机app websocket



| Tables | 说明                            |
| ------ | ----------------------------- |
| URL    | ws://wsdriver.chanmao.ca:7474 |
| Type   | WebSocket                     |
| 是否需要登录 | 是                             |

接口信息:

| type        | scenario      | data                      | description                              |
| ----------- | ------------- | ------------------------- | ---------------------------------------- |
| MDWamp      | subscribed    |                           |                                          |
| MDWamp      | authFail      |                           |                                          |
| MDWamp      | closedSession |                           |                                          |
| MDWamp      | callFail      |                           |                                          |
| MDWamp      | ord_in        |                           |                                          |
| call MDWamp | driver_status | [token, #status,location] | #status 'ON'online 'OFF'offline          |
| call MDWamp | ord_change    | [token, oid, #change]     | #change:'P'pickup 'D'delivering  'S'credit card |
| MDWamp      | ord_out       | [oid]                     |                                          |

