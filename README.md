# kvm-vm-with-hidden-hypervisor

requirements: kvm with libvirt manager

1. leere vm mit usb als boot option erstellen und ressourcen zuweisen
2. in der xml config die cpuid vom wirt übernehmen und den hypervisor verstecken:
    <features>
        <acpi/>
        <apic/>
        <kvm>
          <hidden state="on"/>
        </kvm>
        <vmport state="off"/>
      </features>
      <cpu mode="host-model" check="partial">
        <feature policy="disable" name="hypervisor"/>
      </cpu>
