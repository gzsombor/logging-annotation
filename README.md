logging-annotation
==================

Simple active annotation for Xtend, which automaticly generate helper methods for logging 
for various frameworks. Currently it is possible to switch between using
 * java.util.logging
 * slf4j (logback)
 * plain log4j

Usage:

    @Logging(type="Slf4J")
    class Slf4jTest {
    	def method() {
    		info [|"hello world!"]
    		debug [|"logging "]		
    	}	
    }

or 

    @Logging(type="JavaUtilLogging")
    class JULTest {
        def method() {
            info [|"hello world!"]
            debug [|"logging "]		
        }	
    }

or

    @Logging(type="Log4J")
    class Log4jTest {
        def method() {
            info [|"hello world!"]
            debug [|"logging "]		
        }	
    }

where the info and debug methods take a lambda method, which only called, if the actual logging level is enabled.
Unfortunately, due for a bug, the 'type' in the annotation must be a string, and can't be an enumeration.

