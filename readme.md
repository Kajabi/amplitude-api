# Amplitude API
[![Build Status](https://travis-ci.org/toothrot/amplitude-api.svg?branch=master)](https://travis-ci.org/toothrot/amplitude-api)
[![Code Climate](https://codeclimate.com/github/toothrot/amplitude-api/badges/gpa.svg)](https://codeclimate.com/github/toothrot/amplitude-api)
[![Gem Version](https://badge.fury.io/rb/amplitude-api.svg)](http://badge.fury.io/rb/amplitude-api)

## Installation

```sh
gem install amplitude-api
```

## Basic Usage

The following code snippet will immediately track an event to the Amplitude API.

```ruby
# Configure your Amplitude API key
AmplitudeAPI.config.api_key = "abcdef123456"


event = AmplitudeAPI::Event.new({
  user_id: "123",
  event_type: "clicked on home",
  time: Time.now,
  insert_id: 'f47ac10b-58cc-4372-a567-0e02b2c3d479',
  event_properties: {
    cause: "button",
    arbitrary: "properties"
  }
})
AmplitudeAPI.track(event)
```

## User Privacy APIs

The following code snippet will delete a user from amplitude

```ruby
# Configure your Amplitude API key
AmplitudeAPI.config.api_key = "abcdef123456"

# Configure your Amplitude Secret Key
AmplitudeAPI.config.secret_key = "secretMcSecret"

AmplitudeAPI.delete(user_ids: [233],
  requester: "privacy@example.com"
)
```

## Other useful resources
* [Amplitude HTTP Api Documentation](https://amplitude.zendesk.com/hc/en-us/articles/204771828)
* [Segment.io Amplitude integration](https://segment.com/docs/integrations/amplitude/)
