# Hello Publish
This repo demonstrates using `jobs`, `matrix`, and executing `multiple workflows` based on the same commit. All of the published results are aggregated together as a single result set.

[![Matrix](https://github.com/testspace-com/hello.publish/actions/workflows/matrix.yml/badge.svg)](https://github.com/testspace-com/hello.publish/actions/workflows/matrix.yml) [![Jobs ](https://github.com/testspace-com/hello.publish/actions/workflows/jobs.yml/badge.svg)](https://github.com/testspace-com/hello.publish/actions/workflows/jobs.yml) [![Yet Another ](https://github.com/testspace-com/hello.publish/actions/workflows/yetanother.yml/badge.svg)](https://github.com/testspace-com/hello.publish/actions/workflows/yetanother.yml)

The Test Results are [here](http://testspace-com.testspace.com/projects/testspace-com:hello.publish/spaces/main). 

Also check out the [LIVE DASHBOARD](https://demo.testspace.com). 


## Usage
Publish test results, code coverage, and other artifacts with one command. Seamless integration with your CI. Manage all your test statuses with a single dashboard providing history, metrics, and other types of insights. 

 ```yml
 steps:
   - uses: testspace-com/setup-testspace@v1
      with:
        domain: ${{github.repository_owner}}
        token: ${{ secrets.TESTSPACE_TOKEN }} # optional, only required for private repos
   ..
   - name: Publish Results to Testspace
     run: testspace testcontent/**/*.xml"
```

#### Input
The Testspace client action requires a `domain` and optionally a token for publishing test results.

* [Testspace domain](https://help.testspace.com/dashboard/admin-signup#github) is the **organizational** name (*subdomain*) used when creating the account along with *.testspace.com*. The *.testspace.com* string is optional. 
* [Testspace access token](https://help.testspace.com/dashboard/admin-user#account) is required when using a `private` repo. 

More details of this sample can be found in the Testspace [Help Tutorial](https://help.testspace.com/tutorial/setup) section.
