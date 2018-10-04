---
title: Solução de problemas de implantação do Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de sua implantação de edição do conector de nuvem.
ms.openlocfilehash: 5dbb046680824f2af72688844914db0096e2ded1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371310"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="2520b-103">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2520b-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="2520b-104">Solucionar problemas de sua implantação de edição do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2520b-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="2520b-p101">Este tópico descreve soluções para problemas comuns em implantações do Cloud Connector Edition. Se você está tendo problemas com chamadas de entrada e saída PSTN (Rede Telefônica Pública Comutada), poderá investigar seguindo as soluções descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2520b-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="2520b-107">Conector de nuvem fornece mecanismos internos para automaticamente resolver alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="2520b-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="2520b-108">Um processo de detecção automática procura possíveis problemas com os dispositivos do conector de nuvem e, se possível, adota ações corretivas para resolver esses problemas, sem a necessidade de intervenção do administrador.</span><span class="sxs-lookup"><span data-stu-id="2520b-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="2520b-109">O processo de detecção funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2520b-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="2520b-110">**Sequência de detecção:** O serviço de gerenciamento de conector de nuvem executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante.</span><span class="sxs-lookup"><span data-stu-id="2520b-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="2520b-111">No conector de nuvem versão 2.0 e posteriores, o processo de detecção usa o Skype para negócios Corpnet mudança para tomar as conexões do PowerShell para as máquinas do conector de nuvem; para versões anteriores ao 2.0, o processo de detecção usa a opção de gerenciamento de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2520b-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2520b-112">Recuperação automática para o sucesso, deve haver conectividade de rede entre o host e máquinas virtuais sobre o comutador de rede do host.</span><span class="sxs-lookup"><span data-stu-id="2520b-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="2520b-113">Certifique-se de verificar a conectividade de rede para garantir a detecção automática e recuperação funcionem.</span><span class="sxs-lookup"><span data-stu-id="2520b-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="2520b-114">**Monitoring:** Os seguintes serviços são monitorados no conector de nuvem versão 2.0 e posteriores:</span><span class="sxs-lookup"><span data-stu-id="2520b-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="2520b-115">Máquinas virtuais não estão conectadas à nuvem conector corporativo ou switches virtuais da Internet</span><span class="sxs-lookup"><span data-stu-id="2520b-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="2520b-116">Máquinas virtuais são em um status salvo ou parado</span><span class="sxs-lookup"><span data-stu-id="2520b-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="2520b-117">Serviços de servidor de gerenciamento central: réplica, mestre</span><span class="sxs-lookup"><span data-stu-id="2520b-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="2520b-118">Serviços de servidor de mediação: réplica, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="2520b-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="2520b-119">Serviços de servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="2520b-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="2520b-120">As regras são desabilitadas para CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação de firewall de entrada</span><span class="sxs-lookup"><span data-stu-id="2520b-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="2520b-121">No conector de nuvem versão 1.4.2, somente os seguintes serviços são monitorados:</span><span class="sxs-lookup"><span data-stu-id="2520b-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="2520b-122">Serviços de servidor de mediação: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="2520b-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="2520b-123">Serviço do servidor de borda: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="2520b-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="2520b-124">**Processo de recuperação:** Se todos os serviços monitorados estão desativados, um aparelho é marcado para baixo e serviços foram interrompidos e marcados manuais até que todos os problemas que podem ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="2520b-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="2520b-125">Isto evitará chamadas do roteamento em um dispositivo que pode causar falhas de chamada.</span><span class="sxs-lookup"><span data-stu-id="2520b-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="2520b-126">O serviço de gerenciamento de conector de nuvem repetirá a recuperação automática da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="2520b-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="2520b-127">O intervalo de repetição inicial é a cada dez segundos com um tempo de intervalo máximo de uma hora.</span><span class="sxs-lookup"><span data-stu-id="2520b-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="2520b-128">Para as tentativas de três primeiros recuperação, o intervalo de tempo é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="2520b-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="2520b-129">O intervalo de tempo a partir do quarto repetir, aumenta em duas vezes o anterior intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="2520b-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="2520b-130">Por exemplo, o quarto repetir ocorrerá em 20 segundos, o quinto em 40 segundos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2520b-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="2520b-131">Quando é atingido o tempo de intervalo máximo de uma hora, tentativas continuarão uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="2520b-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="2520b-132">Quando a recuperação for bem-sucedida, as contagens de intervalo e repetição são definidas com seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="2520b-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="2520b-133">Se o serviço de gerenciamento for reiniciado, as contagens de intervalo e repetição são redefinidas para seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="2520b-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="2520b-134">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="2520b-134">Troubleshooting</span></span>

<span data-ttu-id="2520b-135">Estes são soluções para problemas comuns encontrados:</span><span class="sxs-lookup"><span data-stu-id="2520b-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="2520b-136">**Problema: a implantação falha ou para de responder durante a execução dos scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou está incorreto para a NIC de Gerenciamento/Interna/Externa.**</span><span class="sxs-lookup"><span data-stu-id="2520b-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="2520b-137">**Resolução:** Esse problema não pode ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="2520b-138">Desligue e remova essas VMs no Gerenciador do Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="2520b-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="2520b-139">Depois, execute estes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="2520b-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="2520b-140">**Problema: após a instalação do Servidor do Active Directory e da floresta, o Servidor CMS e/ou o Servidor de Mediação não ingressou(aram) corretamente no domínio.**</span><span class="sxs-lookup"><span data-stu-id="2520b-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="2520b-141">**Resolução:** para resolver esse problema, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2520b-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="2520b-142">Faça logon no Servidor do Active Directory e verifique se o domínio foi criado corretamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="2520b-143">Faça logon no servidor CMS/Servidor de Mediação e verifique se foi atribuído um endereço IP válido à NIC da rede corporativa e se um DNS e um IP estático válidos foram configurados como endereço IP do servidor do AD.</span><span class="sxs-lookup"><span data-stu-id="2520b-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="2520b-144">Faça logon no servidor de mediação de CMS/e abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2520b-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="2520b-145">Certificar-se de que você pode fazer o ping o endereço IP e FQDN do servidor do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2520b-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="2520b-146">Se não estiver, pode haver um conflito de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2520b-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="2520b-147">Tente atribuir um novo IP do Active Directory e atualizar o DNS no servidor de mediação de CMS/adequadamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="2520b-148">**Problema: Você recebe a seguinte mensagem de erro "Remove-VMSwitch: Falha ao remover o comutador virtual de Ethernet. Comutador virtual 'Nuvem conector gerenciamento alternar' não pode ser excluído, pois ele está sendo usado por máquinas virtuais em execução ou atribuído a pools filho."**</span><span class="sxs-lookup"><span data-stu-id="2520b-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="2520b-149">**Resolução:** A "nuvem conector gerenciamento opção" não foi excluída após a implantação.</span><span class="sxs-lookup"><span data-stu-id="2520b-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="2520b-150">Se você entrar com esse erro, vá para o Gerenciador Hyper-v e verifique se há ainda não uma máquina virtual que ainda está conectada a ela.</span><span class="sxs-lookup"><span data-stu-id="2520b-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="2520b-151">Se houver máquinas virtuais ainda conectadas, desconecte-los e exclua a opção de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2520b-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="2520b-152">Se a opção de gerenciamento ainda não pode ser excluída, reinicie o servidor de host e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="2520b-153">**Problema: Você recebe a seguinte mensagem de erro, "serviço RTCMRAUTH falhou ao iniciar. Verifique se que o serviço não está desabilitado."**</span><span class="sxs-lookup"><span data-stu-id="2520b-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2520b-154">Esse problema só se aplica às versões de conector de nuvem anteriores a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2520b-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="2520b-p110">A falha de inicialização também pode ocorrer porque já foi feito failover desse Servidor Front-End (usando o failover do computador). Se for o caso, invoque o failback (usando o failback do computador).</span><span class="sxs-lookup"><span data-stu-id="2520b-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="2520b-p111">**Resolução:** esse problema acontece no Servidor de Borda quando o Certificado de Autoridade de Certificação raiz ou o Certificado de Autoridade de Certificação intermediário não é confiável para o Servidor de Borda. Mesmo que o certificado externo possa ser importado, a cadeia de certificados está desfeita. Nessa situação, não é possível iniciar o serviço RTCMRAUTH e/ou RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="2520b-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="2520b-p112">Importe manualmente o Certificado de Autoridade de Certificação raiz e todos os Certificados de Autoridade de Certificação intermediários de seu certificado externo para o Servidor de Borda e reinicie o Servidor de Borda. Depois que os serviços RTCMRAUTH e RTCSRV forem iniciados no Servidor de Borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o seguinte cmdlet para alternar para a nova implantação:</span><span class="sxs-lookup"><span data-stu-id="2520b-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="2520b-162">**Problema: o servidor host foi reiniciado durante a aplicação de atualizações do Windows e ocorrem falhas nas chamadas atendidas pelo servidor.**</span><span class="sxs-lookup"><span data-stu-id="2520b-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="2520b-p113">**Resolução:** se você tiver implantado um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a transferir um computador host (instância de implantação) para dentro ou para fora da topologia atual durante a verificação e a instalação manual da atualização do Windows. Para fazer isso, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="2520b-165">No servidor host, inicie um console do PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="2520b-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="2520b-166">Verifique se há atualizações e instale as que estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2520b-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="2520b-167">No console do PowerShell, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2520b-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="2520b-168">**Problema: quando é feita uma chamada do Cliente Skype for Business usando um número PSTN, não é possível escalonar a chamada para uma conferência por meio de um convite a outro número PSTN.**</span><span class="sxs-lookup"><span data-stu-id="2520b-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="2520b-169">**Resolução:** Para resolver esse problema, consulte [hybrid online de configurar as configurações do servidor de mediação](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="2520b-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="2520b-170">**Problema: durante a instalação do servidor do Active Directory, é exibida esta mensagem de aviso sobre o Windows Update: "A atualização automática do Windows não está habilitada. Para verificar se a função ou o recurso recém-instalado é atualizado automaticamente, ative o Windows Update."**</span><span class="sxs-lookup"><span data-stu-id="2520b-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="2520b-171">**Resolução:** Iniciar uma sessão do PowerShell remoto do inquilino usando Skype para credenciais de administrador de locatário de negócios, e em seguida, execute o seguinte cmdlet para verificar a configuração de _EnableAutoUpdate_ do seu site:</span><span class="sxs-lookup"><span data-stu-id="2520b-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="2520b-172">Se _EnableAutoUpdate_ estiver definida como **True**, você pode ignorar com segurança essa mensagem de aviso, porque o serviço CCEManagement manipulará baixando e instalando atualizações do Windows para máquinas virtuais e o servidor host.</span><span class="sxs-lookup"><span data-stu-id="2520b-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="2520b-173">Se _EnableAutoUpdate_ estiver definida como **False**, execute o seguinte cmdlet para defini-la como **True**.</span><span class="sxs-lookup"><span data-stu-id="2520b-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="2520b-p115">Como opção, você pode verificar e instalar as atualizações manualmente. Consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="2520b-p115">Alternatively, you can manually check for and install updates. See the next section.</span></span>
    
- <span data-ttu-id="2520b-176">**Problema: Você recebe uma mensagem de erro: não é possível registrar appliance porque sua configuração atual de entrada/ \<SiteName\> ou \<ApplianceName\> ou \<FQDN do servidor de mediação\> ou \<endereço de IP do servidor de mediação \> está em conflito com appliance(s) existente. Remover o aparelho de conflito ou atualizar suas informações de entrada/configuração e registre novamente. ' Register-CcAppliance para registrar o aparelho atual para online quando é executado.**</span><span class="sxs-lookup"><span data-stu-id="2520b-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="2520b-177">**Resolução:** Valores para o \<ApplianceName\>, \<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> deve ser exclusivo e somente ela usados para o registro de um dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2520b-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="2520b-178">Por padrão, \<ApplianceName\> proveniente o nome do host.</span><span class="sxs-lookup"><span data-stu-id="2520b-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="2520b-179">\<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> definida no arquivo ini de configuração.</span><span class="sxs-lookup"><span data-stu-id="2520b-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="2520b-180">Por exemplo, ao usar (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para se registrar em SiteName=MySite, se houver um dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), haverá um conflito.</span><span class="sxs-lookup"><span data-stu-id="2520b-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="2520b-181">Primeiro, verifique o arquivo CloudConnector.ini na seção do diretório ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="2520b-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="2520b-182">Você receberá \<SiteName\>, \<FQDN do servidor de mediação\> e \<endereço de IP do servidor de mediação\> valores no arquivo.</span><span class="sxs-lookup"><span data-stu-id="2520b-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="2520b-183">\<ApplianceName\> é o nome do seu servidor de host.</span><span class="sxs-lookup"><span data-stu-id="2520b-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="2520b-184">Em segundo lugar, início locatário PowerShell remoto usando seu Skype para credenciais de administrador de locatário de negócios, em seguida, execute o seguinte cmdlet para verificar a appliance(s) registrados.</span><span class="sxs-lookup"><span data-stu-id="2520b-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="2520b-185">Depois de identificar os conflitos, você poderá atualizar o arquivo CloudConnector.ini com informações compatíveis com o dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.</span><span class="sxs-lookup"><span data-stu-id="2520b-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="2520b-186">**Problema: O cmdlet Get-CcRunningVersion retorna um valor vazio se não houver um aparelho implantado em execução no host.**</span><span class="sxs-lookup"><span data-stu-id="2520b-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="2520b-p118">**Resolução:** isso pode acontecer quando você atualiza da versão 1.3.4 ou 1.3.8 para a versão 1.4.1. Depois de instalar a verão 1.4.1 com o .msi, é necessário executar `Register-CcAppliance` antes de executar qualquer outro cmdlet. `Register-CcAppliance` fará a migração do arquivo module.ini de %UserProfile%\CloudConnector para %ProgramData%\CloudConnector. Se ele tiver sido perdido, um novo module.ini será criado na pasta %ProgramData%\CloudConnector, substituindo as informações da versão em execução/de backup para 1.3.4 ou 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="2520b-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="2520b-191">Compare os arquivos module.ini das pastas %UserProfile%\CloudConnector e %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="2520b-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="2520b-192">Se houver diferenças, exclua o arquivo de module.ini em %ProgramData%\CloudConnector e novamente `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="2520b-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="2520b-193">Você também pode modificar o arquivo manualmente para a execução correta e a versão de backup.</span><span class="sxs-lookup"><span data-stu-id="2520b-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="2520b-194">**Problema: Após executar o cmdlet CcVersion a opção para alternar para uma versão antiga que é diferente da versão atual do script, há não há suporte de alta disponibilidade para essa versão antiga.**</span><span class="sxs-lookup"><span data-stu-id="2520b-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="2520b-195">**Resolução:** Por exemplo, você tiver atualizado de 1.4.1 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2520b-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="2520b-196">Sua versão atual do script, que pode ser determinado executando `Get-CcVersion`e a sua versão em execução, que pode ser determinado executando `Get-CcRunningVersion` são ambos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2520b-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="2520b-197">Neste momento, se você executar `Switch-CcVersion` para a versão em execução voltar para 1.4.1, em seguida, não haverá nenhum suporte à alta disponibilidade para esta versão antiga.</span><span class="sxs-lookup"><span data-stu-id="2520b-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="2520b-p121">Para ter suporte completo para Alta Disponibilidade, alterne novamente para a versão 1.4.2. Assim, a versão em execução e a versão do script serão iguais. Se houver problemas com a implantação da versão 1.4.2, desinstale-a e instale-a novamente assim que possível.</span><span class="sxs-lookup"><span data-stu-id="2520b-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="2520b-200">**Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão prestes a expirar ou estão comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="2520b-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="2520b-p122">**Resolução:** os certificados da autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.</span><span class="sxs-lookup"><span data-stu-id="2520b-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2520b-203">No conector de nuvem versão 2.0 e posteriores, o cmdlet renovar-CcServerCertificate foi alterado para CcServerCertificate de atualização e o cmdlet renovar-CcCACertificate foi alterado para CcCACertificate de atualização.</span><span class="sxs-lookup"><span data-stu-id="2520b-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="2520b-204">Se os certificados internos emitidos para o repositório de gerenciamento Central, o servidor de mediação e o servidor de borda estão prestes a expirar ou comprometida, executem o CcServerCertificate de renovação ou o cmdlet Update-CcServerCertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="2520b-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="2520b-205">Se os certificados de autoridade de certificação estão próximo a expiração, execute o cmdlet renovar-CcCACertificate ou CcCACertificate de atualização para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="2520b-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="2520b-206">**Se os certificados de autoridade de certificação estão comprometidos e se houver apenas um appliance no site,** execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="2520b-207">Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="2520b-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="2520b-208">Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="2520b-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="2520b-209">Para versões do conector de nuvem antes 2.0:</span><span class="sxs-lookup"><span data-stu-id="2520b-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="2520b-210">Ou para a versão do conector de nuvem 2.0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="2520b-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. <span data-ttu-id="2520b-211">Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="2520b-211">Run the Exit-CcUpdate cmdlet to start services and and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="2520b-212">Execute o cmdlet Export-CcRootCertificate no arquivo local no dispositivo e depois copie e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="2520b-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="2520b-213">**Se os certificados de autoridade de certificação estão comprometidos e há vários appliances no site,** execute as seguintes etapas de sequenciais em cada dispositivo no site.</span><span class="sxs-lookup"><span data-stu-id="2520b-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="2520b-214">A Microsoft recomenda que você execute essas etapas durante os períodos de uso não sejam de pico.</span><span class="sxs-lookup"><span data-stu-id="2520b-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
   - <span data-ttu-id="2520b-215">No primeiro appliance, execute o cmdlet Remove-CcCertificationAuthorityFile para a autoridade de certificação de limpeza fazer backup de arquivos no \<SiteRoot\> directory.</span><span class="sxs-lookup"><span data-stu-id="2520b-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
   - <span data-ttu-id="2520b-216">Execute o cmdlet Enter-CcUpdate para esvaziar serviços e coloque cada aparelho no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="2520b-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
   - <span data-ttu-id="2520b-217">Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="2520b-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="2520b-218">Para versões do conector de nuvem antes 2.0:</span><span class="sxs-lookup"><span data-stu-id="2520b-218">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="2520b-219">Ou para a versão do conector de nuvem 2.0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="2520b-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - <span data-ttu-id="2520b-220">No primeiro appliance, execute o seguinte cmdlet para fazer backup dos arquivos de autoridade de certificação para o \<SiteRoot\> pasta.</span><span class="sxs-lookup"><span data-stu-id="2520b-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="2520b-221">Posteriormente, em todos os outros dispositivos no mesmo site, o cmdlet Reset-CcCACertificate consumirá automaticamente os arquivos de backup de autoridade de certificação e appliances usará o mesmo certificado raiz.</span><span class="sxs-lookup"><span data-stu-id="2520b-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```

   - <span data-ttu-id="2520b-222">Execute o cmdlet sair-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="2520b-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
   - <span data-ttu-id="2520b-223">Se o TLS é usado entre o gateway e o servidor de mediação, executar o cmdlet Export-CcRootCertificate a partir de qualquer aparelho no site e, em seguida, instale o certificado exportado seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="2520b-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="2520b-224">**Problema: Você recebe a seguinte mensagem de erro no Log de serviço de gerenciamento de conector nuvem "C:\Program Files\Skype para negócios nuvem conector Edition\ManagementService\CceManagementService.log": erro CceService: 0: exceção inesperada quando relatórios de status online: System.Management.Automation.CmdletInvocationException: falha de Logon para o usuário \<Administrador Global do locatário\>. Crie um novo objeto de credencial, certificando-se de que você usou o nome correto do usuário e a senha. ---\>**</span><span class="sxs-lookup"><span data-stu-id="2520b-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="2520b-225">**Resolução:** As credenciais de administrador de locatário global do Office 365 foram alteradas desde que o aparelho de nuvem conector foi registrado.</span><span class="sxs-lookup"><span data-stu-id="2520b-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="2520b-226">Para atualizar as credenciais armazenadas localmente no dispositivo do conector de nuvem, execute o seguinte do PowerShell do administrador no dispositivo do host:</span><span class="sxs-lookup"><span data-stu-id="2520b-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="2520b-227">**Problema: Depois de alterar a senha para a conta do servidor de host usado para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: especificado da chave não é válido para uso no estado." na %ProgramFiles%\Skype para o Business Connector de nuvem Edition\ManagementService\CceManagementService.log ou enquanto executa o cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="2520b-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="2520b-228">**Resolução:** Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="2520b-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="2520b-229">Quando a senha no servidor host for alterado, você precisará atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="2520b-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="2520b-230">**Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="2520b-231">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="2520b-231">Restart the host server.</span></span>
    
  2. <span data-ttu-id="2520b-232">Exclua o arquivo a seguir: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="2520b-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="2520b-233">Iniciar um console do PowerShell como administrador e execute "Register-CcAppliance-Local" digitem novamente as senhas seguindo a descrição.</span><span class="sxs-lookup"><span data-stu-id="2520b-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="2520b-234">Insira as mesmas senhas que você inseriu antes para a implantação do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="2520b-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="2520b-235">**Se você estiver executando o conector de nuvem versão 2.0 ou posterior,** regenerar todas as senhas de conector de nuvem, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="2520b-236">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="2520b-236">Restart the host server.</span></span>
    
  5. <span data-ttu-id="2520b-237">Exclua o arquivo a seguir: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="2520b-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="2520b-238">Iniciar um console do PowerShell como administrador e execute "Register-CcAppliance-Local" digitem novamente as senhas seguindo a descrição.</span><span class="sxs-lookup"><span data-stu-id="2520b-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="2520b-p127">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha do VMAdmin como a senha do CceService quando ela for solicitada. Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.</span><span class="sxs-lookup"><span data-stu-id="2520b-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="2520b-241">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas de DomainAdmin e VMAdmin forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="2520b-242">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2520b-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="2520b-243">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="2520b-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="2520b-244">Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2520b-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="2520b-245">Se o arquivo de senha armazenada em cache foi gerado com o conector de nuvem versão 2.0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha como CceService.</span><span class="sxs-lookup"><span data-stu-id="2520b-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="2520b-246">Se você alterou as senhas DomainAdmin e VMAdmin, você deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="2520b-247">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2520b-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="2520b-248">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="2520b-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="2520b-249">Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2520b-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="2520b-250">Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2520b-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="2520b-251">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="2520b-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="2520b-252">Quando for solicitada a nova credencial da conta, insira a senha do VmAdmin usada anteriormente. </span><span class="sxs-lookup"><span data-stu-id="2520b-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="2520b-253">**Problema: Com o conector de nuvem versão 2.1 e posterior, quando executado Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro, como: "For Each-Object: A propriedade 'Comum' não pode ser localizado neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="2520b-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="2520b-254">**Resolução:** Conector 2.1 em nuvem e posteriormente requer o .NET Framework 4.6.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2520b-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="2520b-255">Atualize o .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute o cmdlet(s) novamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="2520b-256">**Problema: Com a nuvem conector Edition 2.1, ao se executar Install-CcAppliance, você recebe uma mensagem de erro, como: "Falha ao instalar a nova instância com erro: não é possível definir o"Estado", porque apenas cadeias de caracteres podem ser usadas como valores para definir propriedades de XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="2520b-256">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="2520b-257">**Resolução:** Em Cloudconnector.ini, na seção [comuns], adicione o config "Estado" como a seguir: CountryCode = US State = WA cidade = Redmond</span><span class="sxs-lookup"><span data-stu-id="2520b-257">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="2520b-258">Não é obrigatório para a linha "Estado" ter valor, no entanto, a linha "Estado" não pode ser removida do arquivo Cloudconnector.ini exe.</span><span class="sxs-lookup"><span data-stu-id="2520b-258">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="2520b-259">**Problema: Você recebe a seguinte mensagem de erro "Dismount-WindowsImage: Dismount-WindowsImage falhou. Código de erro = 0xc1550115 "ao instalar ou atualizar a edição do conector de nuvem.**</span><span class="sxs-lookup"><span data-stu-id="2520b-259">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="2520b-260">**Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-limpeza-Wim'".</span><span class="sxs-lookup"><span data-stu-id="2520b-260">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="2520b-261">Isso irá limpar todas as imagens problemáticas.</span><span class="sxs-lookup"><span data-stu-id="2520b-261">This will clean up all troubled images.</span></span> <span data-ttu-id="2520b-262">Execute novamente o Install-CcAppliance ou espere os bits atualizar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-262">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="2520b-263">**Problema: Falha de implantação do aparelho de conector de nuvem primeiro em um ambiente de alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="2520b-263">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="2520b-264">**Resolução:** As etapas executadas dependem do motivo pelo qual a implantação falhou:</span><span class="sxs-lookup"><span data-stu-id="2520b-264">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="2520b-265">Se o primeiro appliance de nuvem conector falha e você não consegue determinar o motivo da falha, instale o aparelho novamente até que a implantação for bem-sucedido e, em seguida, instale os outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2520b-265">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="2520b-266">Se o primeiro appliance de nuvem conector falhar com um problema secundário, como um problema de certificado externo, você poderá corrigir o problema sem instalar novamente o aparelho.</span><span class="sxs-lookup"><span data-stu-id="2520b-266">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="2520b-267">Você pode usar o PowerShell remoto para marcar a implantação como bem-sucedida da seguinte maneira de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="2520b-267">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="2520b-268">(Você pode também usar as etapas a seguir se a primeira implantação foi bem-sucedida, mas, por algum motivo, o conector de nuvem falhar relatar a implantação como um sucesso.)</span><span class="sxs-lookup"><span data-stu-id="2520b-268">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="2520b-269">Para obter a identidade (GUID) do primeiro aparelho de conector de nuvem, execute o cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="2520b-269">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="2520b-270">Para marcar o aparelho implantado como com êxito, execute o Set-CsCceApplianceDeploymentStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2520b-270">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="2520b-271">**Problemas: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**</span><span class="sxs-lookup"><span data-stu-id="2520b-271">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="2520b-p132">**Resolução:** é recomendável utilizar as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização automática do sistema operacional é habilitada, o servidor host e as máquinas virtuais verificarão e instalarão as atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2520b-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="2520b-p133">Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas nesta seção correspondentes ao seu tipo de implantação. Planeje a atualização simultânea do servidor host e das máquinas virtuais executadas nele para minimizar o tempo de inatividade necessário para as atualizações.</span><span class="sxs-lookup"><span data-stu-id="2520b-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="2520b-p134">Se preferir, é possível usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações para os servidores do Cloud Connector. Mas certifique-se de configurar o Windows Update para **não** instalar nada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="2520b-278">Para obter informações sobre como atualizar manualmente a implantação do Cloud Connector, consulte a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="2520b-278">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="2520b-279">**Problema: Quando o conector de nuvem atualiza para uma nova compilação, cmdlets de conector de nuvem não serão atualizados.**</span><span class="sxs-lookup"><span data-stu-id="2520b-279">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="2520b-280">Às vezes, isso acontecerá se uma janela do PowerShell permanecerá aberta quando ocorre a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="2520b-280">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="2520b-281">**Resolução:** Para carregar os cmdlets atualizados, você pode fazer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2520b-281">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="2520b-282">Feche o PowerShell no dispositivo do conector de nuvem e reabra PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2520b-282">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="2520b-283">Ou, você pode executar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="2520b-283">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="2520b-284">**Problema: "o termo 'Stop-CsWindowsService' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável." Erro ao tentar executar o cmdlet CcUpdate de Enter.**</span><span class="sxs-lookup"><span data-stu-id="2520b-284">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="2520b-285">**Resolução:** Exclua o arquivo de HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.</span><span class="sxs-lookup"><span data-stu-id="2520b-285">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="2520b-286">PowerShell cria esse arquivo como um cache de cmdlets de módulos encontrados para que ele não precisa analisar novamente todos os módulos de cada vez como que tornaria coisas realmente lento.</span><span class="sxs-lookup"><span data-stu-id="2520b-286">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="2520b-287">Provavelmente, houve alguns corrupção de arquivo que forneceu resultados incorretos ao PowerShell quando ele estava lendo volta de nesse cache.</span><span class="sxs-lookup"><span data-stu-id="2520b-287">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="2520b-288">**Problema: "Import-Module CloudConnector" gerará o erro "Import-Module: O módulo especificado"CloudConnector"não foi carregado, porque nenhum arquivo de módulo válido foi encontrado em qualquer diretório módulo"**</span><span class="sxs-lookup"><span data-stu-id="2520b-288">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="2520b-289">**Resolução:** esse problema não pode ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2520b-289">**Resolution:**</span></span>
    - <span data-ttu-id="2520b-290">Validar se realmente o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="2520b-290">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="2520b-291">Após validar esse módulo CloudConnector existe sob este local, a variável de ambiente PSModulePath armazenar o caminho para os locais dos módulos pode ser alterada:</span><span class="sxs-lookup"><span data-stu-id="2520b-291">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="2520b-292">a.</span><span class="sxs-lookup"><span data-stu-id="2520b-292">a.</span></span> <span data-ttu-id="2520b-293">Alteração temporária: iniciar o Powershell como administrador e execute o seguinte comando: $env: PSModulePath = $env: PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="2520b-293">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="2520b-294">b.</span><span class="sxs-lookup"><span data-stu-id="2520b-294">b.</span></span> <span data-ttu-id="2520b-295">Para alterar persistente, inicie o PowerShell como administrador e executar os seguintes comandos, um por um: $CurrentValue = [ambiente]:: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules","Computador")</span><span class="sxs-lookup"><span data-stu-id="2520b-295">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="2520b-296">Instalar atualizações do Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="2520b-296">Install Windows updates manually</span></span>

<span data-ttu-id="2520b-297">Caso não queira usar atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="2520b-297">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="2520b-298">Talvez seja necessário reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="2520b-298">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="2520b-299">Quando um servidor host está reiniciando, os usuários não poderão usar o conector de nuvem para fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="2520b-299">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="2520b-300">Você pode verificar e instalar as atualizações manualmente para controlar quando isso é feito e depois reiniciar os computadores conforme necessário, no momento mais conveniente, para evitar a interrupção dos serviços.</span><span class="sxs-lookup"><span data-stu-id="2520b-300">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="2520b-301">Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="2520b-301">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="2520b-302">Selecione **sistema e segurança \>Windows Update**e, em seguida, gerenciar as atualizações e o servidor for reiniciado conforme apropriado para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="2520b-302">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="2520b-303">Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="2520b-303">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="2520b-304">Selecione **sistema e segurança \>Windows Update**e, em seguida, configure as atualizações e o servidor for reiniciado conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="2520b-304">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="2520b-p142">Se houver mais de um dispositivo no site, os usuários não poderão acessar a instância que está sendo atualizada e reiniciada durante as atualizações. Eles serão conectados a outras instâncias da implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções do serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e restaurá-la depois da conclusão. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="2520b-p142">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="2520b-309">Em cada servidor host, abra um console do PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="2520b-309">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="2520b-310">Remova a instância da alta disponibilidade usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2520b-310">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="2520b-311">Siga as etapas para uma única instância para aplicar as atualizações e reiniciar a máquina virtual manualmente.</span><span class="sxs-lookup"><span data-stu-id="2520b-311">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="2520b-312">Defina a instância novamente para alta disponibilidade com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2520b-312">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="2520b-313">Para implantações de vários sites, siga as etapas referentes a um único site para cada site da implantação, aplicando as atualizações a um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2520b-313">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="2520b-314">Dicas ao instalar o software antivírus na máquina host conector de nuvem</span><span class="sxs-lookup"><span data-stu-id="2520b-314">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="2520b-315">Se você precisa instalar o software antivírus na máquina host conector de nuvem, você precisa adicionar as exclusões a seguintes:</span><span class="sxs-lookup"><span data-stu-id="2520b-315">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="2520b-316">Diretório de aparelho de local em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="2520b-316">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="2520b-317">Diretório de Site remoto em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="2520b-317">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="2520b-318">Diretório de Site local na máquina hospeda a pasta raiz do site compartilhado.</span><span class="sxs-lookup"><span data-stu-id="2520b-318">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="2520b-319">%ProgramFiles%\Skype para o conector de nuvem Business Edition</span><span class="sxs-lookup"><span data-stu-id="2520b-319">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="2520b-320">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="2520b-320">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="2520b-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="2520b-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="2520b-322">O processo Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="2520b-322">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
