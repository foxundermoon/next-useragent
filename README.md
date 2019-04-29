# next-useragent

`next-useragent` parses browser user-agent strings for [next.js](https://nextjs.org/).

[![npm](https://nodei.co/npm/next-useragent.png?downloads=true&stars=true)](https://nodei.co/npm/next-useragent)

## Installation

```
$ npm install next-useragent
```

## Usage

`next-useragent` is simple to use.  
Give access to user-agent details anywhere using `withUserAgent` method.

* Passed as an `ua` property in the context of the `getInitialProps` method.
* Providing the following props to your component as `ua`.

Example usage:

```
import React from 'react'
import { UserAgentProps, parse } from 'next-useragent'

class IndexPage extends React.Component<UserAgentProps> {

  static async getInitialProps(ctx) {
    // ctx.ua
    // => `UserAgent` type object.

    return {}
  }

  render() {
    const { ua } = this.props

    return (
      <ul>
        <li>Original source: { ua.source }</li>
        <li>Device Type: { ua.deviceType }</li>
        <li>Device Vendor: { ua.deviceVendor }</li>
        <li>OS Name: { ua.os }</li>
        <li>OS Version: { ua.osVersion }</li>
        <li>Browser Name: { ua.browser }</li>
        <li>Browser Version: { ua.browserVersion }</li>
        <li>is iPhone?: { ua.isIphone ? 'yes' : 'no' }</li>
        <li>is iPad?: { ua.isIpad ? 'yes' : 'no' }</li>
        <li>is mobile?: { ua.isMobile ? 'yes' : 'no' }</li>
        <li>is tablet?: { ua.isTablet ? 'yes' : 'no' }</li>
        <li>is desktop?: { ua.isDesktop ? 'yes' : 'no' }</li>
        <li>is Chrome?: { ua.isChrome ? 'yes' : 'no' }</li>
        <li>is Firefox?: { ua.isFirefox ? 'yes' : 'no' }</li>
        <li>is Safari?: { ua.isSafari ? 'yes' : 'no' }</li>
        <li>is Internet Explorer?: { ua.isIE ? 'yes' : 'no' }</li>
        <li>is Mac?: { ua.isMac ? 'yes' : 'no' }</li>
        <li>is ChromeOS?: { ua.isChromeOS ? 'yes' : 'no' }</li>
        <li>is Windows?: { ua.isWindows ? 'yes' : 'no' }</li>
        <li>is iOS?: { ua.isIos ? 'yes' : 'no' }</li>
        <li>is Android?: { ua.isAndroid ? 'yes' : 'no' }</li>
        <li>is bot?: { ua.isBot ? 'yes' : 'no' }</li>
      </ul>
    )
  }
}

export default withUserAgent(IndexPage)
```

## License

`next-useragent` is licensed under MIT License.  
See [LICENSE](https://github.com/tokuda109/next-useragent/blob/master/LICENSE) for more information.
