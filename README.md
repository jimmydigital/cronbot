NAME
    cronbot - Gain more control over your cron jobs and how they run.

SYNOPSIS
    cronbot <options> [full path to your regular cron job]

       Options:
         --rand xx          Add a max random number of minutes to wait before starting job. Default is 30 minutes
                            if not otherwise specified. 
         --dulicate         Allow this job to run more than once
         --timer xx         Specify a max execution time. Longer than this and it will be killed hard
         --nonice           Do not run the job through nice (man nice)
         --man              Full man page

USAGE
    15 * * * * root /usr/local/bin/cronbot --timer 90 --rand 10
    /usr/local/bin/rsync -a /home /mnt/remote/home

    This would attempt to run rsync every hour but will not start a
    duplicate job if it's still running. It will hard kill the job if it's
    running for more than 90 minutes and it will add a random delay between
    1 and 10 minutes before starting the job.

DESCRIPTION
    Cronbot is a wrapper script for cron jobs. Rather than running your
    job/script directly you run it through cronbot and it will allow a
    little more control to help keep things from getting out of hand. The
    default behavior is to only allow one instance of your job to run. This
    can be changed with the --duplicate option. You can also pass in a
    maximum time of execution for a job or add a random amount time to delay
    the start of your job. Also by default jobs are run with a default
    'nice' value which is usually 10 (man nice).

COPYRIGHT AND LICENSE
    Copyright 2013 Jared Watkins

    This is released under the GNU General Public License (GPL-2.0)

AVAILABILITY
    Get it at:

    <https://github.com/jimmydigital/cronbot>

    or

    <http://jaredwatkins.com/>

