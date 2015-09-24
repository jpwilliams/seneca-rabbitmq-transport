seneca-rabbitmq-transport-v2
======================

Seneca micro-services message transport over RabbitMQ messaging.
Contains some updates (including message acknowledgement) as the main repo wasn't bein updated!


## Support

For questions:
[@rjrodger](http://twitter.com/rjrodger)
[@zbangazbanga](http://twitter.com/zbangazbanga)
[@atticjack](http://twitter.com/atticjack)

Current Version: 0.2.2

Tested on: Node 4.1.1, Seneca 0.6.5


### Install

```sh
npm install seneca-rabbitmq-transport-v2
```

You'll also need [RabbitMQ](http://www.rabbitmq.com) or another server that
implements version 0.9.1+ of the [AMQP](http://www.amqp.org) protocol.


## Quick Example

```js
require('seneca')()
  .use('rabbitmq-transport')
  .add('foo:two',function(args,done){ done(null,{bar:args.bar}) })
  .client( {type:'rabbitmq',url:'amqp://localhost',pin:'foo:one,bar:*'} )
  .listen( {type:'rabbitmq',url:'amqp://localhost',pin:'foo:two,bar:*'} )
```






