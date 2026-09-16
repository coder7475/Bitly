# Bitly

A URL shortening service that converts long URLs to shorter, manageable links. 

## Core/Functional Requirements

    1. Users should be able to submit a long URL and receive a shortened version
        - Optionally, users should be able to specify a custom alias for their shortened URL (ie. "www.short.ly/my-custom-alias")
        - Optionally, users should be able to specify an expiration date for their shortened URL. 
    2. Users should be able to access the original URL by using the shortened URL.

### Out of Scope

    1. User authentication and account management.
    2. Analytics on link clicks (e.g., click counts, geographic data).

## Non-Functional Requirements

    1. The system should ensure uniqueness for the short codes (each short code maps to exactly one long URL)
    2. The redirection should occur with minimal delay (< 100ms)
    3. The system should be reliable and available 99.99% of the time (availability > consistency)
    4. The system should scale to support 1B shortened URLs and 100M DAU

### Out of scope
    
    1. Data consistency in real-time analytics.
    2. Advanced security features like spam detection and malicious URL filtering.


## Back of the envelope estimation

- Write Operation: 100 million URLs generated per day
- Write operation per second: 100 million / 24 /3600 = 1160
- Read operation: Assuming ratio of read operation to write operation is 10:1, read operation per second: 1160 * 10 = 11,600
- Assuming the URL shortener service will run for 10 years, this means we must support 100 million * 365 * 10 = 365 billion records.
- Assume average URL length is 100.
- Storage requirement over 10 years: 365 billion * 100 bytes = 36.5 TB















