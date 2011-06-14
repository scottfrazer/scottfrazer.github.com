---
title: Home
layout: main
---

Test
====
{% highlight java %}
import java.net.*;
import java.io.*;

public class serve
{
    public static void main(String args[])
    {
        try
        {
            ServerSocket server = new ServerSocket( 80 );
            Socket connection = server.accept();
            OutputStream out = connection.getOutputStream();
            out.write("HTTP/1.1 200 OK\r\n\r\n".getBytes());
            out.write("Hello World!  My Web Server Works!".getBytes());
            out.flush();
            connection.close();
        }
        catch (Exception e)
        {
            System.err.println("Error: " + e);
        }
    }
}
{% endhighlight %}
