SoftwareFirewallBypass
======================

Finds a trusted process (one with an open socket handle) and uses process injection to leverage it's trust setting.

This was designed against tools like ZoneAlarm which users "trust" to open a socket. As the process is altered in memory
the hash of the executable on disc doesn't change, therefore it wasn't registered as modified.

This worked on XP. I suspect with UAC it no longer works, but is a good example of iterating over open handles in windows, and injecting C into another process using CreateRemoteThread (and fixing up the reloc table of the current module to do so).
