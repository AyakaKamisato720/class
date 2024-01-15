let CoronaCoin = require('coronacoin')

let cc = new CoronaCoin({
  token: '...', // токен от CoronaCoin
  userToken: '...' // токен от пользователя, для метода startPolling
})

cc.startPolling().then(
  () => console.log('Started socketing') // начинаем обработку платежей
)

cc.events.on(
  'transfer',
  event => console.log(event) // { from_id: number, amount: number }
)