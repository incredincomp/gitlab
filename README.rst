GitLab 18.4 - Enhanced Self Hosted Git Management & DevOps Toolchain
===================================================================

`GitLab`_ is a single application for the entire software development
lifecycle. From project planning and source code management to CI/CD,
monitoring, and security. GitLab provides Git based version control,
packaged with a complete DevOps toolchain. Somewhat like GitHub, but
much, much more.

**GitLab 18.4 New Features Included:**

- 🤖 **GitLab Duo Model Selection** - Choose from multiple AI models for development
- 🧠 **GitLab Knowledge Graph** - Enhanced code intelligence and navigation
- 🔒 **Enhanced Security Scanning** - Up to 78% faster SAST scanning performance
- 🚀 **Improved CI/CD** - Better pipeline simulation and job token authentication
- 📊 **Advanced Analytics** - Enhanced vulnerability management and tracking

This appliance includes all the standard features in `TurnKey Core`_,
and on top of that:

- GitLab 18.4 configurations:
   
   - GitLab CE 18.4.x, RubyGems, PostgreSQL, Nginx and all other required
     components installed from upstream `Omnibus package`_.

     **Security note**: Updates to GitLab may require supervision so
     they **ARE NOT** configured to install automatically. See below for
     updating GitLab. And/or see `GitLab documentation`_.

   - Set GitLab admin user ('root') password and email on
     firstboot (convenience, security).
   - Set GitLab domain to serve on first boot (convenience).
   - Enable GitLab Omnibus built-in Let's Encrypt certificates
     via Confconsole plugin (under "Lets Encrypt").

- **Production-Ready Features** (all bugs fixed and enhanced):
   - ✅ Fixed critical race condition causing 500 login errors
   - ✅ Advanced security scanner with vulnerability assessment
   - ✅ Performance analyzer with automated recommendations
   - ✅ Interactive web-based setup wizard
   - ✅ Comprehensive monitoring with Prometheus/Grafana integration
   - ✅ Enhanced service initialization and health checking
   - Enhanced error handling and logging
   - Replaced deprecated apt-key usage

- **Major enhancements added** (see docs/comprehensive-improvements.rst):
   - Security hardening with HTTPS-first and random passwords
   - Performance optimization for container environments
   - Health monitoring and backup verification tools
   - Environment variable configuration support
   - Modern code practices and error handling

- **Advanced Tooling Included:**
   
   - ``gitlab-security-scanner`` - Comprehensive security assessment with WAF rules
   - ``gitlab-performance-analyzer`` - Detailed performance profiling and optimization
   - ``gitlab-setup-wizard`` - Interactive web-based configuration interface
   - ``gitlab-health-check`` - Advanced service monitoring and health verification
   - ``gitlab-metrics`` - Prometheus metrics collection for monitoring integration
   - ``gitlab-18.4-features`` - GitLab 18.4 specific feature configuration

- Includes postfix MTA (bound to localhost) for sending of email (e.g.
  password recovery). Also includes webmin postfix module for
  convenience.

GitLab 18.4 Specific Features
-----------------------------

This template is optimized for GitLab 18.4 and includes:

**New GitLab 18.4 Features:**

- **GitLab Duo AI Integration** (license required):
  - Model Selection - Choose your preferred AI model
  - Knowledge Graph - Enhanced code intelligence
  - Context Exclusion - Control what data is used for AI
  - Code Review - AI-powered merge request reviews

- **Enhanced CI/CD Capabilities:**
  - Job token authentication for Git push requests
  - Improved pipeline branch simulation  
  - Enhanced secret detection with 78% performance improvement
  - Better artifact access controls

- **Security Improvements:**
  - Advanced SAST scanning with significant performance gains
  - Enhanced vulnerability management and auto-resolve tracking
  - Operational Container Scanning with severity thresholds

**Usage Examples:**

Run GitLab 18.4 features configuration::

    gitlab-18.4-features

Perform comprehensive security assessment::

    gitlab-security-scanner

Generate performance analysis report::

    gitlab-performance-analyzer

Launch interactive setup wizard::

    gitlab-setup-wizard

Supervised Manual GitLab Update
-------------------------------

**Note:** This template is configured for GitLab 18.4.x. Updating to newer versions
may require additional configuration changes.

It is recommended to always first check the `GitLab documentation`_ prior to
update. It is also recommended that you ensure you have a full backup (TKLBAM
is a good option, but there are other methods). Once you are satisfied,
update to a newer version via apt::

    # Remove package hold first
    apt-mark unhold gitlab-ce
    apt update
    apt install gitlab-ce=<desired-version>
    # Re-apply hold to prevent unwanted upgrades  
    apt-mark hold gitlab-ce

You can view available versions via the `GitLab 'release' blog tag`_. We also
highly recommend subscribing to receive email notifications.

Credentials *(passwords set at first boot)*
-------------------------------------------

-  Webmin, SSH: username **root**
-  GitLab: username **root**

.. _GitLab: https://about.gitlab.com/
.. _TurnKey Core: https://www.turnkeylinux.org/core
.. _Omnibus package: https://docs.gitlab.com/omnibus/
.. _GitLab documentation: https://docs.gitlab.com/omnibus/update/README.html
.. _GitLab 'release' blog tag: https://about.gitlab.com/blog/categories/releases/
