---
title: Solução de problemas de implantação do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de implantação da edição do Cloud Connector.
ms.openlocfilehash: 1049ec2f8f3b85c71c7b9203916b79764e9be161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286720"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="a40a8-103">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a40a8-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="a40a8-104">Solucionar problemas de implantação da edição do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a40a8-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="a40a8-p101">Este tópico descreve soluções para problemas comuns em implantações do Cloud Connector Edition. Se você está tendo problemas com chamadas de entrada e saída PSTN (Rede Telefônica Pública Comutada), poderá investigar seguindo as soluções descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="a40a8-107">O Cloud Connector fornece mecanismos internos para resolver automaticamente alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="a40a8-108">Um processo de detecção automática procura possíveis problemas com o Cloud Connector appliances e, se possível, toma uma ação corretiva para solucionar esses problemas sem a necessidade de intervenção do administrador.</span><span class="sxs-lookup"><span data-stu-id="a40a8-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="a40a8-109">O processo de detecção funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a40a8-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="a40a8-110">**Sequência de detecção:** O serviço de gerenciamento do conector de nuvem executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante.</span><span class="sxs-lookup"><span data-stu-id="a40a8-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="a40a8-111">No Cloud Connector versão 2,0 e posterior, o processo de detecção usa a opção corpnet do Skype for Business para fazer conexões do PowerShell com os computadores do conector de nuvem; para versões anteriores ao 2,0, o processo de detecção usa a opção de gerenciamento do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="a40a8-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a40a8-112">Para que a recuperação automática seja bem-sucedida, deve haver conectividade de rede entre o host e máquinas virtuais no switch de rede do host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="a40a8-113">Certifique-se de verificar a conectividade da rede para garantir que a detecção automática e a recuperação possam ser bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="a40a8-114">**Monitoramento:** Os seguintes serviços são monitorados na versão 2,0 do Cloud Connector e posterior:</span><span class="sxs-lookup"><span data-stu-id="a40a8-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="a40a8-115">Máquinas virtuais não estão conectadas aos comutadores de nuvem corporativos ou virtuais da Internet</span><span class="sxs-lookup"><span data-stu-id="a40a8-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="a40a8-116">As máquinas virtuais estão em um status salvo ou parado</span><span class="sxs-lookup"><span data-stu-id="a40a8-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="a40a8-117">Serviços do servidor central de gerenciamento: réplica, mestre</span><span class="sxs-lookup"><span data-stu-id="a40a8-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="a40a8-118">Serviços do servidor de mediação: réplica, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="a40a8-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="a40a8-119">Serviços do servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="a40a8-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="a40a8-120">As regras de firewall de entrada estão desabilitadas para CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="a40a8-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="a40a8-121">Na versão 1.4.2 do conector de nuvem, somente os seguintes serviços são monitorados:</span><span class="sxs-lookup"><span data-stu-id="a40a8-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="a40a8-122">Serviços do servidor de mediação: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="a40a8-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="a40a8-123">Serviço do servidor de borda: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="a40a8-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="a40a8-124">**Processo de recuperação:** Se algum serviço monitorado estiver inoperante, um dispositivo será marcado para baixo e os serviços serão interrompidos e marcados como manual até que todos os problemas possam ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="a40a8-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="a40a8-125">Isso impedirá chamadas do roteamento para um dispositivo que pode causar falhas na chamada.</span><span class="sxs-lookup"><span data-stu-id="a40a8-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="a40a8-126">O serviço de gerenciamento do conector de nuvem tentará automaticamente a recuperação automática da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="a40a8-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="a40a8-127">O intervalo inicial de repetição é a cada dez segundos com um tempo máximo de intervalo de uma hora.</span><span class="sxs-lookup"><span data-stu-id="a40a8-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="a40a8-128">Para as três primeiras tentativas de recuperação, o intervalo de tempo é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a40a8-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="a40a8-129">A partir da quarta repetição, o tempo do intervalo aumenta em duas vezes o tempo anterior do intervalo.</span><span class="sxs-lookup"><span data-stu-id="a40a8-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="a40a8-130">Por exemplo, a quarta tentativa ocorrerá em 20 segundos, a quinta em 40 segundos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a40a8-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="a40a8-131">Quando o tempo máximo de intervalo de uma hora for atingido, as tentativas continuarão uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="a40a8-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="a40a8-132">Quando a recuperação é bem-sucedida, os números intervalo e repetição são definidos como seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="a40a8-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="a40a8-133">Se o serviço de gerenciamento for reiniciado, o intervalo e os números de repetição serão redefinidos para seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="a40a8-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="a40a8-134">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="a40a8-134">Troubleshooting</span></span>

<span data-ttu-id="a40a8-135">Veja a seguir as soluções para problemas freqüentes encontrados:</span><span class="sxs-lookup"><span data-stu-id="a40a8-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="a40a8-136">**Problema: a implantação falha ou para de responder durante a execução dos scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou está incorreto para a NIC de Gerenciamento/Interna/Externa.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="a40a8-137">**Resolução:** Esse problema não pode ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="a40a8-138">Desligue e remova essas VMs no Gerenciador do Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="a40a8-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="a40a8-139">Depois, execute estes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a40a8-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="a40a8-140">**Problema: após a instalação do Servidor do Active Directory e da floresta, o Servidor CMS e/ou o Servidor de Mediação não ingressou(aram) corretamente no domínio.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="a40a8-141">**Resolução:** para resolver esse problema, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a40a8-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="a40a8-142">Faça logon no Servidor do Active Directory e verifique se o domínio foi criado corretamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="a40a8-143">Faça logon no servidor CMS/Servidor de Mediação e verifique se foi atribuído um endereço IP válido à NIC da rede corporativa e se um DNS e um IP estático válidos foram configurados como endereço IP do servidor do AD.</span><span class="sxs-lookup"><span data-stu-id="a40a8-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="a40a8-144">Faça logon no servidor CMS/mediação e abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="a40a8-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="a40a8-145">Verifique se é possível executar ping no FQDN e no endereço IP do Servidor do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a40a8-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="a40a8-146">Se não o for, talvez haja um conflito de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="a40a8-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="a40a8-147">Tente atribuir um novo IP ao Active Directory e atualize apropriadamente o DNS no Servidor CMS/Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="a40a8-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="a40a8-148">**Problema: você recebe a seguinte mensagem de erro: "Remove-VMSwitch: falha ao remover o comutador Ethernet virtual. A opção de gerenciamento do conector de nuvem do comutador virtual ' não pode ser excluída porque está sendo usada executando máquinas virtuais ou atribuídas a pools filho. "**</span><span class="sxs-lookup"><span data-stu-id="a40a8-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="a40a8-149">**Resolução:** A "opção de gerenciamento do conector de nuvem" não foi excluída após a implantação.</span><span class="sxs-lookup"><span data-stu-id="a40a8-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="a40a8-150">Se você clicar nesse erro, vá para o Gerenciador do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ele.</span><span class="sxs-lookup"><span data-stu-id="a40a8-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="a40a8-151">Se houver máquinas virtuais ainda conectadas, desconecte-as e exclua a opção de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a40a8-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="a40a8-152">Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="a40a8-153">**Problema: você recebe a seguinte mensagem de erro: "o serviço RTCMRAUTH falhou ao iniciar. Verifique se o serviço não está desabilitado. "**</span><span class="sxs-lookup"><span data-stu-id="a40a8-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a40a8-154">Esse problema só se aplica a versões anteriores a 1.4.2 do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a40a8-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="a40a8-p110">A falha de inicialização também pode ocorrer porque já foi feito failover desse Servidor Front-End (usando o failover do computador). Se for o caso, invoque o failback (usando o failback do computador).</span><span class="sxs-lookup"><span data-stu-id="a40a8-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="a40a8-p111">**Resolução:** esse problema acontece no Servidor de Borda quando o Certificado de Autoridade de Certificação raiz ou o Certificado de Autoridade de Certificação intermediário não é confiável para o Servidor de Borda. Mesmo que o certificado externo possa ser importado, a cadeia de certificados está desfeita. Nessa situação, não é possível iniciar o serviço RTCMRAUTH e/ou RTCSRV.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="a40a8-p112">Importe manualmente o Certificado de Autoridade de Certificação raiz e todos os Certificados de Autoridade de Certificação intermediários de seu certificado externo para o Servidor de Borda e reinicie o Servidor de Borda. Depois que os serviços RTCMRAUTH e RTCSRV forem iniciados no Servidor de Borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o seguinte cmdlet para alternar para a nova implantação:</span><span class="sxs-lookup"><span data-stu-id="a40a8-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="a40a8-162">**Problema: o servidor host foi reiniciado durante a aplicação de atualizações do Windows e ocorrem falhas nas chamadas atendidas pelo servidor.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="a40a8-p113">**Resolução:** se você tiver implantado um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a transferir um computador host (instância de implantação) para dentro ou para fora da topologia atual durante a verificação e a instalação manual da atualização do Windows. Para fazer isso, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="a40a8-165">No servidor host, inicie um console do PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="a40a8-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="a40a8-166">Verifique se há atualizações e instale as que estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a40a8-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="a40a8-167">No console do PowerShell, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a40a8-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="a40a8-168">**Problema: quando é feita uma chamada do Cliente Skype for Business usando um número PSTN, não é possível escalonar a chamada para uma conferência por meio de um convite a outro número PSTN.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="a40a8-169">**Resolução:** Para solucionar esse problema, consulte [definir as configurações do servidor de mediação híbrida online](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="a40a8-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="a40a8-170">**Problema: durante a instalação do servidor do Active Directory, é exibida esta mensagem de aviso sobre o Windows Update: "A atualização automática do Windows não está habilitada. Para verificar se a função ou o recurso recém-instalado é atualizado automaticamente, ative o Windows Update."**</span><span class="sxs-lookup"><span data-stu-id="a40a8-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="a40a8-171">**Resolução:** Inicie uma sessão do PowerShell remoto de locatário usando as credenciais de administrador de locatários do Skype for Business e execute o seguinte cmdlet para verificar a configuração do _EnableAutoUpdate_ do seu site:</span><span class="sxs-lookup"><span data-stu-id="a40a8-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="a40a8-172">Se _EnableAutoUpdate_ for definido como **true**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement manipulará o download e a instalação das atualizações do Windows para as máquinas virtuais e o servidor host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="a40a8-173">Se _EnableAutoUpdate_ estiver definido como **false**, execute o cmdlet a seguir para defini-lo como **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="a40a8-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="a40a8-174">Como opção, você pode verificar e instalar as atualizações manualmente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="a40a8-175">Consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="a40a8-175">See the next section.</span></span>
    
- <span data-ttu-id="a40a8-176">**Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque o \<endereço\> IP \<do servidor\> ou \<o FQDN\> ou o \<endereço IP do servidor de MEDIANAME ou servidor de mediação atual \> em conflito com os aparelhos existentes. Remova o dispositivo de conflito ou atualize as informações de entrada/configuração e registre-se novamente. ' When Run-CcAppliance para registrar o aplicativo atual para online.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="a40a8-177">**Resolução:** Os valores para \<o reaparelhoname\> \<, o\> servidor \<de mediador de\> servidor FQDN e o endereço IP do servidor de mediação devem ser exclusivos e apenas usados para um registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a40a8-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="a40a8-178">Por padrão, \<o nome\> do aplicativo vem do nome do host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="a40a8-179">\<Endereço\> IP do\> servidor \<de mediação e FQDN do servidor de mediação definido no arquivo ini de configuração.</span><span class="sxs-lookup"><span data-stu-id="a40a8-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="a40a8-180">Por exemplo, ao usar (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) para se registrar em SiteName=MySite, se houver um dispositivo registrado (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), haverá um conflito.</span><span class="sxs-lookup"><span data-stu-id="a40a8-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="a40a8-181">Primeiro, verifique o arquivo CloudConnector.ini na seção do diretório ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="a40a8-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="a40a8-182">Você obterá \<os\>valores \<de endereço\> IP\> do \<SiteName do servidor de mediação e do SiteName do servidor de mediação no arquivo.</span><span class="sxs-lookup"><span data-stu-id="a40a8-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="a40a8-183">\<Appliancename\> é o nome do seu servidor host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="a40a8-184">Em seguida, inicie o PowerShell Remote locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para verificar o (s) dispositivo (s) registrado (s).</span><span class="sxs-lookup"><span data-stu-id="a40a8-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="a40a8-185">Depois de identificar os conflitos, você poderá atualizar o arquivo CloudConnector.ini com informações compatíveis com o dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.</span><span class="sxs-lookup"><span data-stu-id="a40a8-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="a40a8-186">**Problema: o cmdlet Get-CcRunningVersion retorna um valor vazio se houver um dispositivo implantado em execução no host.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="a40a8-187">**Resolução:** Isso pode acontecer quando você atualiza do 1.3.4 ou do 1.3.8 para o 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="a40a8-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="a40a8-188">Depois de instalar a versão 1.4.1 com o. msi, você deve `Register-CcAppliance` executar antes de executar qualquer outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a40a8-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="a40a8-189">`Register-CcAppliance`migrará o arquivo module. ini de%UserProfile%\CloudConnector para%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="a40a8-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="a40a8-190">Se você a perdeu, um novo module. ini será criado na pasta%ProgramData%\CloudConnector e substituirá as informações sobre a versão de execução/backup do 1.3.4 ou do 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="a40a8-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="a40a8-191">Compare os arquivos module.ini das pastas %UserProfile%\CloudConnector e %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="a40a8-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="a40a8-192">Se houver diferenças, exclua o arquivo module. ini no%ProgramData%\CloudConnector e execute `Register-CcAppliance`novamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="a40a8-193">Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.</span><span class="sxs-lookup"><span data-stu-id="a40a8-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="a40a8-194">**Problema: depois de executar o cmdlet switch-CcVersion para alternar para uma versão antiga diferente da versão do script atual, não há suporte de alta disponibilidade para esta versão antiga.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="a40a8-195">**Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a40a8-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="a40a8-196">Sua versão de script atual, que pode ser determinada pela `Get-CcVersion`execução, e sua versão em execução, que pode ser determinada `Get-CcRunningVersion` pela execução é de ambos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a40a8-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="a40a8-197">Nesse momento, se você executar `Switch-CcVersion` a versão de execução novamente no 1.4.1, não haverá suporte de alta disponibilidade para esta versão antiga.</span><span class="sxs-lookup"><span data-stu-id="a40a8-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="a40a8-p121">Para ter suporte completo para Alta Disponibilidade, alterne novamente para a versão 1.4.2. Assim, a versão em execução e a versão do script serão iguais. Se houver problemas com a implantação da versão 1.4.2, desinstale-a e instale-a novamente assim que possível.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="a40a8-200">**Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão prestes a expirar ou estão comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="a40a8-p122">**Resolução:** os certificados da autoridade de certificação do Skype for Business são válidos por cinco anos. Os certificados internos emitidos para o Repositório de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a40a8-203">No Cloud Connector versão 2,0 e posterior, o cmdlet Renew-CcServerCertificate mudou para Update-CcServerCertificate, e o cmdlet Renew-CcCACertificate mudou para Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="a40a8-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="a40a8-204">Se certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e Edge Server estiverem próximos de expiração ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="a40a8-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="a40a8-205">Se os certificados de autoridade de certificação estiverem prestes a expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="a40a8-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="a40a8-206">**Se os certificados de autoridade de certificação estiverem comprometidos e houver apenas um dispositivo no site,** execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="a40a8-207">Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a40a8-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="a40a8-208">Execute os seguintes cmdlets para redefinir e criar novos certificados da autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="a40a8-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="a40a8-209">Para versões do conector de nuvem antes de 2,0:</span><span class="sxs-lookup"><span data-stu-id="a40a8-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="a40a8-210">Ou para o Cloud Connector Release 2,0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="a40a8-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="a40a8-211">Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate do aparelho e instale o certificado exportado em seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="a40a8-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="a40a8-212">Você também pode ser solicitado a emitir novamente o certificado em seu gateway.</span><span class="sxs-lookup"><span data-stu-id="a40a8-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="a40a8-213">Execute o cmdlet Exit-CcUpdate para iniciar serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a40a8-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```
   Exit-CcUpdate
   ```


    <span data-ttu-id="a40a8-214">**Se os certificados de autoridade de certificação estiverem comprometidos e houver vários dispositivos no site,** execute as seguintes etapas sequenciais em cada aplicativo do site.</span><span class="sxs-lookup"><span data-stu-id="a40a8-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="a40a8-215">A Microsoft recomenda que você execute essas etapas durante horários de uso sem pico.</span><span class="sxs-lookup"><span data-stu-id="a40a8-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="a40a8-216">No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da CA no diretório \<SiteRoot\> .</span><span class="sxs-lookup"><span data-stu-id="a40a8-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="a40a8-217">Execute o cmdlet Enter-CcUpdate para drenar serviços e colocar cada utilitário no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a40a8-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="a40a8-218">No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="a40a8-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="a40a8-219">Para versões do conector de nuvem antes de 2,0:</span><span class="sxs-lookup"><span data-stu-id="a40a8-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="a40a8-220">Ou para o Cloud Connector Release 2,0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="a40a8-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="a40a8-221">No primeiro dispositivo, execute o cmdlet a seguir para fazer backup dos arquivos da CA para \<a\> pasta SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="a40a8-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="a40a8-222">Em todos os outros aplicativos do mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os aplicativos usem o mesmo certificado raiz e, em seguida, solicite novos certificados.</span><span class="sxs-lookup"><span data-stu-id="a40a8-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="a40a8-223">Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e instale o certificado exportado em seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="a40a8-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="a40a8-224">Você também pode ser solicitado a emitir novamente o certificado em seu gateway.</span><span class="sxs-lookup"><span data-stu-id="a40a8-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="a40a8-225">Execute o cmdlet Exit-CcUpdate para iniciar serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="a40a8-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="a40a8-226">**Problema: você recebe a seguinte mensagem de erro no log do serviço de gerenciamento do Cloud Connector, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService erro: 0: exceção inesperada quando status de relatório para online: System. Management. Automation. CmdletInvocationException: falha no logon para \<o administrador\>de locatário global do usuário. Crie um novo objeto Credential, certificando-se de que você usou o nome de usuário e a senha corretos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="a40a8-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="a40a8-227">**Resolução:** As credenciais de administrador de locatário global do Office 365 foram alteradas desde que o dispositivo do conector de nuvem foi registrado.</span><span class="sxs-lookup"><span data-stu-id="a40a8-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="a40a8-228">Para atualizar as credenciais armazenadas localmente no aparelho do Cloud Connector, execute o seguinte do administrador do PowerShell no dispositivo host:</span><span class="sxs-lookup"><span data-stu-id="a40a8-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="a40a8-229">**Problema: depois de alterar a senha da conta do servidor host que você usou para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: a chave não é válida para uso no estado especificado." no%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou durante a execução do cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="a40a8-230">**Resolução:** Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="a40a8-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="a40a8-231">Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="a40a8-232">**Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="a40a8-233">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="a40a8-234">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="a40a8-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="a40a8-235">Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="a40a8-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="a40a8-236">Insira as mesmas senhas que você inseriu anteriormente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a40a8-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="a40a8-237">**Se você estiver executando o Cloud Connector versão 2,0 ou posterior,** gere novamente todas as senhas do conector de nuvem seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="a40a8-238">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="a40a8-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="a40a8-239">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="a40a8-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="a40a8-240">Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="a40a8-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="a40a8-p128">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha do VMAdmin como a senha do CceService quando ela for solicitada. Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="a40a8-243">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas de DomainAdmin e VMAdmin forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="a40a8-244">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a40a8-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="a40a8-245">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="a40a8-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="a40a8-246">Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="a40a8-247">Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2,0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService.</span><span class="sxs-lookup"><span data-stu-id="a40a8-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a40a8-248">Se você tiver alterado as senhas do DomainAdmin e VMAdmin, deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="a40a8-249">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a40a8-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="a40a8-250">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="a40a8-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="a40a8-251">Quando for solicitada a nova credencial da conta, insira a senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="a40a8-252">Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a40a8-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="a40a8-253">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="a40a8-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="a40a8-254">Quando for solicitada a nova credencial da conta, insira a senha do VmAdmin usada anteriormente. </span><span class="sxs-lookup"><span data-stu-id="a40a8-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="a40a8-255">**Problema: com o Cloud Connector versão 2,1 e posterior, ao executar Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "para cada objeto: a propriedade ' Common ' não pode ser encontrada nesse objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 carac: 14 "**</span><span class="sxs-lookup"><span data-stu-id="a40a8-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="a40a8-256">**Resolução:** O Cloud Connector 2,1 e posterior exige o .NET Framework 4.6.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="a40a8-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="a40a8-257">Atualize o .NET Framework no aparelho para a versão 4.6.1 ou posterior e execute o (s) cmdlet (s) novamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="a40a8-258">**Problema: com o Cloud Connector Edition 2,1, ao executar install-CcAppliance, você recebe uma mensagem de erro como: "falha ao instalar nova instância com erro: não é possível definir" State "porque apenas cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="a40a8-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="a40a8-259">**Resolução:** No Cloudconnector. ini, na seção [Common], adicione a configuração "estado" da seguinte maneira: CountryCode = EUA state = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="a40a8-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="a40a8-260">Não é obrigatório para a linha "State" ter valor, mas a linha "State" não pode ser removida do arquivo Cloudconnector. ini.</span><span class="sxs-lookup"><span data-stu-id="a40a8-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="a40a8-261">**Problema: você recebe a seguinte mensagem de erro "Dismount-WindowsImage: Dismount-WindowsImage falhou. Código de erro = 0xc1550115 "ao instalar ou atualizar a edição do conector de nuvem.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="a40a8-262">**Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-Cleanup-wim" ".</span><span class="sxs-lookup"><span data-stu-id="a40a8-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="a40a8-263">Isso limpará todas as imagens problemáticas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-263">This will clean up all troubled images.</span></span> <span data-ttu-id="a40a8-264">Execute Install-CcAppliance novamente ou aguarde a atualização automática dos bits.</span><span class="sxs-lookup"><span data-stu-id="a40a8-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="a40a8-265">**Problema: a implantação do primeiro dispositivo de conector de nuvem em um ambiente de alta disponibilidade falha**</span><span class="sxs-lookup"><span data-stu-id="a40a8-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="a40a8-266">**Resolução:** As etapas que você tomar dependerão do motivo da falha na implantação:</span><span class="sxs-lookup"><span data-stu-id="a40a8-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="a40a8-267">Se o primeiro dispositivo de conector de nuvem falhar e você não puder determinar o motivo da falha, instale o aparelho novamente até que a implantação seja bem-sucedida e, em seguida, instale os outros aparelhos.</span><span class="sxs-lookup"><span data-stu-id="a40a8-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="a40a8-268">Se o primeiro dispositivo de conector de nuvem falhar com um problema secundário, como um problema de certificado externo, talvez você possa corrigir o problema sem reinstalar o aparelho.</span><span class="sxs-lookup"><span data-stu-id="a40a8-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="a40a8-269">Em seguida, você pode usar o PowerShell Remote locatário para marcar a implantação com êxito da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="a40a8-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="a40a8-270">(Você também pode usar as etapas a seguir se a primeira implantação tiver sido bem-sucedida, mas, por algum motivo, o Cloud Connector não conseguir relatar a implantação como sucesso.)</span><span class="sxs-lookup"><span data-stu-id="a40a8-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="a40a8-271">Para obter a identidade (GUID) do primeiro aparelho de conexão de nuvem, execute o cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="a40a8-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="a40a8-272">Para marcar o aparelho como implantado com êxito, execute o set-CsCceApplianceDeploymentStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a40a8-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="a40a8-273">**Problemas: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="a40a8-p133">**Resolução:** é recomendável utilizar as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition. Depois que um dispositivo é registrado para o gerenciamento online e a atualização automática do sistema operacional é habilitada, o servidor host e as máquinas virtuais verificarão e instalarão as atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="a40a8-p134">Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas nesta seção correspondentes ao seu tipo de implantação. Planeje a atualização simultânea do servidor host e das máquinas virtuais executadas nele para minimizar o tempo de inatividade necessário para as atualizações.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="a40a8-p135">Se preferir, é possível usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações para os servidores do Cloud Connector. Mas certifique-se de configurar o Windows Update para **não** instalar nada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="a40a8-280">Para obter informações sobre como atualizar manualmente a implantação do Cloud Connector, consulte a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="a40a8-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="a40a8-281">**Problema: quando o Cloud Connector é atualizado para uma nova compilação, os cmdlets do conector de nuvem não são atualizados.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="a40a8-282">Às vezes, isso acontece se uma janela do PowerShell é deixada aberta quando ocorre a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="a40a8-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="a40a8-283">**Resolução:** Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a40a8-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="a40a8-284">Feche o PowerShell no aparelho do Cloud Connector e, em seguida, abra novamente o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40a8-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="a40a8-285">Ou então, você pode executar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="a40a8-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="a40a8-286">**Problema: "o termo" parar-CsWindowsService "não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa funcional." erro ao tentar executar o cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="a40a8-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="a40a8-287">**Resolução:** Exclua o arquivo \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache do $HOME.</span><span class="sxs-lookup"><span data-stu-id="a40a8-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="a40a8-288">O PowerShell cria esse arquivo como um cache de cmdlets a partir de módulos que ele encontra para que não precise analisá-los novamente todos os módulos, sempre que isso tornaria as coisas realmente lentas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="a40a8-289">Provavelmente, houve uma certa corrupção de arquivo que fornecia resultados enganosas ao PowerShell quando ele estava lendo novamente desse cache.</span><span class="sxs-lookup"><span data-stu-id="a40a8-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="a40a8-290">**Problema: "Import-Module CloudConnector" gera o erro "Import-Module: o módulo especificado" CloudConnector "não foi carregado porque nenhum arquivo de módulo válido foi encontrado em qualquer diretório de módulo"**</span><span class="sxs-lookup"><span data-stu-id="a40a8-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="a40a8-291">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="a40a8-291">**Resolution:**</span></span>
    - <span data-ttu-id="a40a8-292">Valide se o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="a40a8-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="a40a8-293">Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazena o caminho para os locais dos módulos pode ser alterada:</span><span class="sxs-lookup"><span data-stu-id="a40a8-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="a40a8-294">a.</span><span class="sxs-lookup"><span data-stu-id="a40a8-294">a.</span></span> <span data-ttu-id="a40a8-295">Alteração temporária: Inicie o PowerShell como administrador e execute o seguinte comando: $env:P SModulePath = $env:P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="a40a8-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="a40a8-296">b.</span><span class="sxs-lookup"><span data-stu-id="a40a8-296">b.</span></span> <span data-ttu-id="a40a8-297">Para alteração persistente, inicie o PowerShell como administrador e execute os seguintes comandos, um por um: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "máquina") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Arquivos de Files\WindowsPowerShell\Modules "," computador ")</span><span class="sxs-lookup"><span data-stu-id="a40a8-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="a40a8-298">Instalar atualizações do Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="a40a8-298">Install Windows updates manually</span></span>

<span data-ttu-id="a40a8-299">Caso não queira usar atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="a40a8-300">Talvez seja necessário reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="a40a8-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="a40a8-301">Quando um servidor host estiver sendo reiniciado, os usuários não poderão usar o conector de nuvem para fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="a40a8-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="a40a8-302">Você pode verificar e instalar as atualizações manualmente para controlar quando isso é feito e depois reiniciar os computadores conforme necessário, no momento mais conveniente, para evitar a interrupção dos serviços.</span><span class="sxs-lookup"><span data-stu-id="a40a8-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="a40a8-303">Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="a40a8-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="a40a8-304">Selecione **sistema e segurança \>Windows Update**e, em seguida, gerencie as atualizações e reinícios do servidor conforme apropriado para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="a40a8-305">Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="a40a8-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="a40a8-306">Selecione **sistema e segurança \>Windows Update**e, em seguida, configure as atualizações e os reinícios do servidor, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="a40a8-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="a40a8-p143">Se houver mais de um dispositivo no site, os usuários não poderão acessar a instância que está sendo atualizada e reiniciada durante as atualizações. Eles serão conectados a outras instâncias da implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais após a conclusão das atualizações. Para evitar possíveis interrupções do serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e restaurá-la depois da conclusão. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="a40a8-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="a40a8-311">Em cada servidor host, abra um console do PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="a40a8-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="a40a8-312">Remova a instância da alta disponibilidade usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a40a8-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="a40a8-313">Siga as etapas para uma única instância para aplicar as atualizações e reiniciar a máquina virtual manualmente.</span><span class="sxs-lookup"><span data-stu-id="a40a8-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="a40a8-314">Defina a instância novamente para alta disponibilidade com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a40a8-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="a40a8-315">Para implantações de vários sites, siga as etapas referentes a um único site para cada site da implantação, aplicando as atualizações a um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="a40a8-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="a40a8-316">Dicas ao instalar um software antivírus na máquina host do conector da nuvem</span><span class="sxs-lookup"><span data-stu-id="a40a8-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="a40a8-317">Se você precisar instalar um software antivírus na máquina host do conector de nuvem, será necessário adicionar as seguintes exclusões:</span><span class="sxs-lookup"><span data-stu-id="a40a8-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="a40a8-318">Diretório de dispositivos locais em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="a40a8-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="a40a8-319">Diretório de sites remotos em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="a40a8-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="a40a8-320">Diretório de sites local no computador hospeda a pasta raiz do site compartilhado.</span><span class="sxs-lookup"><span data-stu-id="a40a8-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="a40a8-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a40a8-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="a40a8-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="a40a8-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="a40a8-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="a40a8-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="a40a8-324">O processo Microsoft. RTC. CCE. ManagementService. exe.</span><span class="sxs-lookup"><span data-stu-id="a40a8-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
