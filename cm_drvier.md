#cm_driver


```
object:
		{
			result: number,
			message: string,
			driver_id: string,
			uid: string,
			token: string
}```




```
```
object:
        {
        type: string,
        driver_id: string,
        scenrio: string
        }```
	
		
		
```
```
object:
		{
			result: number,
            message: string,
            orders: array[
            0: object:
             {
                oid: string,
           	 order: object
           	        {
                       comment: string,
           	        created: string,
           	        dlexp: string,
           	        oid: string,
           	        rid: string,
           	        status: string,
           	        total:string,
                       __proto__: object
                      }
               rr: object
                      {
                       addr: string,
                       lat: string
                       lng:string,
                       postal: string,
                       tel: string,
                       unit:string
                       __proto__: object
                      }
               user: object
                      {
                       addr: string,
                       buzz: string,
                       lat: string,
                       lng: string,
                       name: string,
                       postal: string,
                       tel :string,
                       unit: string
                      }
             }],
            type: string
		}```
		
		
```
```.headers.Accept:
		{
            Cmos: string | string | string | string,
			Cmuuid: string,
            Cmversion: string,
            authortoken: string
		}```
		
		
```
```
object:
		{
			errorcode: number,
            message: string,
            result: number
        }```
	
```	
```
object:
		{
			driver_id: string,
            message: string,
            result: number,
            token: string,
            uid: string
        }```
