autodock-autoscale
==================

Automatic Scaling Plugin for autodock.

> **note**
>
> See: [autodock](https://github.com/prologic/autodock)

Basic Usage
-----------

Start the daemon:

    $ docker run -d --name autodock prologic/autodock

Run a web container of your choice and set `AUTOSCALE=1`:

    $ docker run -d -e AUTOSCALE=1 prologic/hello

Now autodock-autoscale will monitor this container's load and automatically spawn new instances of this container based on the parameters used to start it.

> **note**
>
> This is best used in conjunction with  
> autodock-hipache \<https://github.com/prologic/autodock-hipache\_
>
Configuration
-------------

There are several options you can pass when running the autodock-autoscale plugin:

-   `AUTOSCALE_MIN=n` The minimum number of instances to run at any given time.
-   `AUTOSCALE_MAX=n` The maximum number of instances to scale up to.

By default `AUTOSCALE_MIN` is set ti the discovered number of containers with `AUTOSCALE=1` set. `AUTOSCALE_MAX` is by default set to the maximum number of detected CPU cores on the Docker host.
