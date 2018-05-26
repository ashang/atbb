--- layout: post title: vsftpd.conf sample date: 2009-02-25 16:34:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: ashang.blogspot.com blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '960161830291882038' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

    # can NOT have SPACE before or after the "=" !!!!
    #
    # The default compiled in settings are very paranoid. This file
    # loosens things up a bit, to make the ftp daemon more usable.
    # Octal numbers are supported for numeric options, use 0 as the first digit
     # Standalone options --------------------------------------
    listen=YES
    #anonymous--------------------------------------------------------------
    anonymous_enable=YES
    #anon_root=/home/ftp/
    #no_anon_password=YES
     anon_other_write_enable=NO
    #perform deletion and renaming. 
    anon_upload_enable=YES
    anon_mkdir_write_enable=YES
    anon_world_readable_only=YES
    #only allow to download files which are world readable. 
    #FTP user may own files, especially in the presence of uploads.
     ####anon_max_rate=10000000
    #
    #Default is 000, so uploaded file cannot be anon readable!!
    anon_umask=022
    #chown_uploads=YES
    #chown_username=ftp
    #ftp_username=ftp
    #max_clients=10
    #listen_port=21
    #max_per_ip=2
     #listen_address
    #tcp_wrappers=YES
    # Performance ---------------------------------------------
    #one_process_model=YES
    # Activates a faster "one process per connection" model. Note! 
    # To maintain security, only available on systems with capabilities
     # less pure security, but gains performance for simultaneously connected users.
    # ls -R may cause excessive I/O resource consuming
    # However, some broken FTP clients such as "ncftp" and "mirror" need it 
     #ls_recurse_enable=YES
    #local user-------------------------------------------------------------
    ##local_root=/home/ftp
    local_enable=YES
    local_umask=022
    # A value of 002 is nice if groups share directories
     #guest_enable=NO
    #guest_username=guest
    #all non-anonymous logins are classed as guest logins, mapped to guest_username
    #operation------------------------------------------------------------------
    write_enable=YES
     #FTP commands which change the filesystem: 
    # STOR,  DELE,  RNFR, RNTO, MKD, RMD, APPE  SITE.
    #messages---------------------------------------------------------
    dirmessage_enable=YES
    #message_file=.messages
     #ftpd_banner= 
    #banner_file=
    #Logging------------------------------------------------------------
    xferlog_enable=YES
    xferlog_std_format=YES
    xferlog_file=/var/log/xferlog
    #written  in  standard xferlog  format,    as used by wu-ftpd. 
     #useful if can reuse existing transfer statistics generators.  
    log_ftp_protocol=YES
    # all FTP requests and responses are logged, providing xferlog_std_format=YES 
    #transfer mode------------------------------------------------------------
     #When  enabled,  ASCII  mode  data transfers will be honoured on  downloads.
    # By default the server will pretend to allow ASCII mode but ignore it.
    # I/O resources may be consumed by command "SIZE /big/file" in ASCII mode.
     # without the DoS risk of SIZE and ASCII downloads. ASCII mangling should be
    # on the client anyway..
    #ascii_download_enable=NO
    # ASCII downloads are CPU heavy
    #ascii_upload_enable=YES
    # to prevent uploaded scripts from breaking or for Windows-users  to upload
     #async_abor_enable=YES
    # Enables older FTP clients to cancel in-progress transfers.
    # FTP clients may hang when cancelling a transfer unless this feature is on.
    # this  feature is awkward to handle
    # Security ------------------------------------------------
     connect_from_port_20=YES
    #          This  controls  whether  PORT style data connections use port 20
    #         (ftp-data) on the server machine.  For  security  reasons,  some
    #         clients  may insist that this is the case. Conversely, disabling
     #        this option enables vsftpd to run with slightly less  privilege.
    #ftp_data_port=20
    #The port from which PORT style connections originate 
    #hide_ids=YES
    # The port  to allocate for PASV style data connections.
     #idle_session_timeout=300
    #data_connection_timeout=120
    #accept_timeout=60
    #The timeout, for connection with a PASV style data connection.
    #connect_timeout=60
    # The  timeout, for a remote client to respond to PORT style data connection.
     ###file_open_mode=0666
    # The permissions with which uploaded files are  created.
    # umasks are applied on top of this value. 
    #userlist_enable=YES
    #userlist_deny=YES
    #userlist_file = /etc/ftpusers
    # If set to NO, then users will be denied login   unless in userlist_file.
     # If YES, never allow users in userlist file, and not even prompt for password.
    # Note that the default vsftpd pam config also checks /etc/vsftpd.ftpusers
    # Useful for combatting certain DoS attacks.
    #deny_email_enable=YES
     #banned_email_file=/etc/vsftpd.banned_emails
    #check_shell=YES
    #only has  an  effect  for  non-PAM  builds  of vsftpd. 
    #check /etc/shells for a    valid user shell for local logins.
    #        The  option  is  the  name  of a file containing a list of local
     #        users which will be placed in a  chroot()  jail  in  their  home
    #         directory.   This   option   is  only  relevant  if  the  option
    #         chroot_list_enable is enabled, and the option  chroot_local_user
     #        is disabled.
    # You may specify an explicit list of local users to chroot() to their home
    # directory. If chroot_local_user is YES, then this list becomes a list of
    # users to NOT chroot().
    #chroot_list_enable=YES
     #chroot_list_file = /etc/vsftpd.chroot_list
    #       If  activated,  you  may  provide  a list of local users who are
    #         placed in a chroot() jail in their home  directory  upon  login.
    #         The meaning is slightly different if chroot_local_user is set to
     #        YES. In this case, the list becomes a list of  users  which  are
    #         NOT  to be placed in a chroot() jail.  By default, the file con-
    #         taining this list is /etc/vsftpd.chroot_list, but you may  over-
     #        ride this with the chroot_list_file setting.
    #chroot_local_user = YES
    #       If  set to YES, local users will be placed in a chroot() jail in
    #         their home directory after  login.   Warning:  This  option  has
     #        security  implications, especially if the users have upload per-
    #         mission, or shell access. Only enable if you know what  you  are
    #         doing.   Note  that  these  security implications are not vsftpd
     #        specific. They apply to all FTP daemons which offer to put local
    #         users in chroot() jails.
    #
    #       passwd_chroot_enable
    #        If enabled, along with chroot_local_user , then a chroot()  jail
     #        location  may be specified on a per-user basis. Each user's jail
    #         is derived from their home directory string in /etc/passwd.  The
    #         occurence  of  /./ in the home directory string denotes that the
     #        jail is at that particular location in the path.
    pasv_enable=YES
    # enable non-passive transfers, Some FTP clients demand this.
    #port_enable=YES
    #       pasv_promiscuous=NO
    #          Set  to  YES if you want to disable the PASV security check that
     #        ensures the data connection originates from the same IP  address
    #         as the control connection.  Only enable if you know what you are
    #         doing! The only legitimate use for  this  is  in  some  form  of
     #        secure tunnelling scheme.
    #       port_promiscuous=NO
    #       Set to YES if you want to disable the PORT security  check  that
    #         ensures  that  outgoing data connections can only connect to the
    #         client. Only enable if you know what you are doing!
     # Set to NO if you want to enhance privacy
    #setproctitle_enable=YES
    #       If enabled, vsftpd will try and show session status  information
    #         in the system process listing. In other words, the reported name
     #        of the process will change to reflect what a vsftpd  session  is
    #         doing  (idle,  downloading etc). You probably want to leave this
    #         off for security purposes.
    #
    #       tcp_wrappers=NO
     #          If enabled, and vsftpd was compiled with  tcp_wrappers  support,
    #         incoming  connections  will  be  fed through tcp_wrappers access
    #         control. Furthermore, there is a mechanism for per-IP based con-
     #        figuration.  If  tcp_wrappers sets the VSFTPD_LOAD_CONF environ-
    #         ment variable, then the vsftpd session will  try  and  load  the
    #         vsftpd configuration file specified in this variable.
    #
     #
    #       text_userdb_names=YES
    #          By  default,  numeric IDs are shown in the user and group fields
    #         of directory listings. You can get  textual  names  by  enabling
    #         this parameter. It is off by default for performance reasons.
     #
    #
    #use_localtime=NO
    #If  enabled, vsftpd will display directory listings with the the
    #time in your local time zone. The default is to display GMT. The
    #times returned by the MDTM FTP command are also affected by this
     #use_sendfile
    #An internal setting used for testing  the   relative  benefit  of
    #using the sendfile() system call on your platform.
    #Default: YES
    # totally isolated and unprivileged user used for vsftpd
    #nopriv_user=ftpsecure
     # pasv_address
    #Use this option to override the  IP  address  that  vsftpd  will
    #advertise     in response to the PASV command. Provide a numeric IP address.
    #Default: (none - the address is taken  from  the  incoming  connected socket)
     secure_chroot_dir=/var/run/vsftpd
    pam_service_name=vsftpd
    #This  option  should  be the name of a directory which is empty.
    #Also, the directory should not be writable by the ftp user. This
    #directory is used as a secure chroot() jail at times vsftpd does
     #not require filesystem access.
    #
    # user_config_dir
    # Allows the override of  any    config  option, on a per-user basis. 
    # If  you  set user_config_dir  to  be /etc/vsftpd_user_conf and then log on as
    # the user "chris", then vsftpd will apply    the  settings  in  the
     # file  /etc/vsftpd_user_conf/chris     for  the duration of the session. 
    rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
    rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/" width="1" height="1" />
