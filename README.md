### remotely
---
https://github.com/wegowise/remotely

```rb
Remotely.configure do
  app :legsapp do
    url "http://somanylegs.com/api/v1"
    basic_auth "username", "password"
    use_middleware Faraday::HttpCache, store: MyCache.new
  end
end

class Millepied < Remotely::Model
  app :legsapp
  uri "/legs"
  
  attr_savable :name, :type
end

class Millepied < ActiveRecord::Base
  has_many_remote :legs
end

class Millepied < ActiveRecord::Base
  has_many_remote :legs, :path => "/store/legs"
end

class Millepied < ActiveRecord::Base
  has_many_remote :legs, :path => "/millepieds/:id/legs"
end

class Millepied < ActiveRecord::Base
  has_many_remote :legs, :app => :legsapp, ...
end

class Person < ActiveRecord::Base
  has_many_remote :legs
end

class Leg < Remotely::Model
  app :legsapp
  uri "/legs"
end

class Millepied < ActiveRecord::Base
  has_many_remote :legs, :path => "/millepieds/:id/legs"
end

m = Millepied.new
m.id
m.legs

Remotely.configure do
  app :legsapp do
    url "http://somanylegs.com/api/v1"
    basic_auth "username", "password"
  end
end

Remotely.configure do
  app :legsapp do
    url "http://somanylegs.com/api/v1"
    token_auth "abcdef", {:foo => 'bar'}
  end
end

Remotely.configure do
  app :legsapp do
    url "http://somanylegs.com/api/v1"
    authorization 'Bearer', 'mF_9.B5f-4.1JqM'
  end
end

Remotely.configure do
  app :legsapp do
    url "http://somanylegs.com/api/v1"
    authorization 'OAuth', {:token => 'abcdef', :foo => 'bar'}
  end
end

m = Millepied.new
m.legs[0]
m.legs[0].length

leg = m.legs.first
leg.user_id
leg.user
```

```
```

```
```


