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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Solucionar problemas de implantação do Cloud Connector Edition.
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220221"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="c35c0-103">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c35c0-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="c35c0-104">Solucionar problemas de implantação do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c35c0-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="c35c0-105">Este tópico descreve soluções para problemas comuns com implantações do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c35c0-105">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="c35c0-106">Se você estiver tendo problemas com chamadas de e para a PSTN (rede telefônica pública comutada), você pode investigar seguindo as soluções descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c35c0-106">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="c35c0-107">O Cloud Connector fornece mecanismos internos para resolver automaticamente alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="c35c0-108">Um processo de detecção automática procura possíveis problemas com os dispositivos do Cloud Connector e, se possível, realiza ações corretivas para resolver esses problemas sem a necessidade de intervenção do administrador.</span><span class="sxs-lookup"><span data-stu-id="c35c0-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="c35c0-109">O processo de detecção funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c35c0-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="c35c0-110">**Sequência de detecção:** O serviço de gerenciamento do Cloud Connector executa um processo a cada 60 segundos para detectar se um dispositivo está inoperante.</span><span class="sxs-lookup"><span data-stu-id="c35c0-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="c35c0-111">No Cloud Connector versão 2,0 e posterior, o processo de detecção usa a opção corpnet do Skype for Business para fazer conexões do PowerShell com as máquinas do Cloud Connector; para versões anteriores a 2,0, o processo de detecção usa a opção de gerenciamento do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c35c0-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c35c0-112">Para que a recuperação automática tenha êxito, deve haver conectividade de rede entre o host e as máquinas virtuais sobre o comutador de rede do host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="c35c0-113">Certifique-se de verificar a conectividade da rede para garantir que a detecção e a recuperação automáticas possam ser bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="c35c0-114">**Monitoramento:** Os seguintes serviços são monitorados no Cloud Connector versão 2,0 e posteriores:</span><span class="sxs-lookup"><span data-stu-id="c35c0-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="c35c0-115">As máquinas virtuais não estão conectadas aos comutadores virtuais corporativos ou de Internet do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c35c0-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="c35c0-116">As máquinas virtuais estão em um status salvo ou parado</span><span class="sxs-lookup"><span data-stu-id="c35c0-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="c35c0-117">Serviços do servidor de gerenciamento central: réplica, mestre</span><span class="sxs-lookup"><span data-stu-id="c35c0-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="c35c0-118">Serviços do servidor de mediação: réplica, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c35c0-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c35c0-119">Serviços do servidor de borda: réplica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="c35c0-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="c35c0-120">As regras de firewall de entrada estão desabilitadas para o CS RTCSRV no servidor de borda, CS RTCMEDSRV no servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="c35c0-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="c35c0-121">No Cloud Connector versão 1.4.2, apenas os seguintes serviços são monitorados:</span><span class="sxs-lookup"><span data-stu-id="c35c0-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="c35c0-122">Serviços do servidor de mediação: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="c35c0-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="c35c0-123">Serviço do servidor de borda: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="c35c0-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="c35c0-124">**Processo de recuperação:** Se quaisquer serviços monitorados estiverem inativos, um dispositivo é marcado para baixo, e os serviços são interrompidos e marcados manualmente até que todos os problemas possam ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="c35c0-125">Isso impedirá chamadas de roteamento para um dispositivo que pode causar falhas de chamada.</span><span class="sxs-lookup"><span data-stu-id="c35c0-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="c35c0-126">O serviço de gerenciamento do Cloud Connector repetirá a recuperação automática da seguinte maneira</span><span class="sxs-lookup"><span data-stu-id="c35c0-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="c35c0-127">O intervalo de repetição inicial é a cada dez segundos com um tempo máximo de intervalo de uma hora.</span><span class="sxs-lookup"><span data-stu-id="c35c0-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="c35c0-128">Para as três primeiras tentativas de recuperação, o intervalo de tempo é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="c35c0-129">A partir da quarta repetição, o tempo do intervalo aumenta em duas vezes o intervalo de tempo anterior.</span><span class="sxs-lookup"><span data-stu-id="c35c0-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="c35c0-130">Por exemplo, a quarta tentativa ocorrerá em 20 segundos, o quinto em 40 segundos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c35c0-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="c35c0-131">Quando o tempo máximo de intervalo de uma hora é atingido, as repetições continuarão uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="c35c0-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="c35c0-132">Quando a recuperação é bem-sucedida, as contagens intervalo e repetição são definidas com seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="c35c0-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="c35c0-133">Se o serviço de gerenciamento for reiniciado, as contagens de intervalo e de repetição serão redefinidas para seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="c35c0-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="c35c0-134">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="c35c0-134">Troubleshooting</span></span>

<span data-ttu-id="c35c0-135">Veja a seguir soluções para problemas comumente encontrados:</span><span class="sxs-lookup"><span data-stu-id="c35c0-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="c35c0-136">**Problema: a implantação falha ou para de responder ao executar scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou incorreto para a NIC de gerenciamento/interna/externa.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="c35c0-137">**Resolução:** Este problema não pode ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="c35c0-138">As NICs não podem ser adicionadas às VMs enquanto estiverem em execução.</span><span class="sxs-lookup"><span data-stu-id="c35c0-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="c35c0-139">Encerre e remova essas VMs no Gerenciador do Hyper-v e execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c35c0-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="c35c0-140">**Problema: após a instalação do servidor do Active Directory e da floresta, o servidor CMS e/ou o servidor de mediação não ingressaram corretamente no domínio.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="c35c0-141">**Resolução:** Para resolver esse problema, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="c35c0-142">Faça logon no servidor do Active Directory e verifique se o domínio foi criado corretamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="c35c0-143">Faça logon no CMS/servidor de mediação e verifique se no corpnet NIC um endereço IP válido é atribuído e se o IP estático e o DNS válidos estão configurados como o endereço IP do servidor do AD.</span><span class="sxs-lookup"><span data-stu-id="c35c0-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="c35c0-144">Faça logon no CMS/servidor de mediação e abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="c35c0-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="c35c0-145">Verifique se é possível executar ping no FQDN e no endereço IP do servidor do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c35c0-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="c35c0-146">Se não for possível, pode haver um conflito de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="c35c0-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="c35c0-147">Tente atribuir um novo IP para o Active Directory e atualizar o DNS no servidor de CMS/mediação apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="c35c0-148">**Problema: você recebe a seguinte mensagem de erro, "Remove-VMSwitch: falha ao remover o comutador Ethernet virtual. O ' comutador de gerenciamento do Cloud Connector ' do comutador virtual não pode ser excluído porque está sendo usado pela execução de máquinas virtuais ou atribuído a pools filho.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="c35c0-149">**Resolução:** A "opção de gerenciamento do Cloud Connector" não foi excluída após a implantação.</span><span class="sxs-lookup"><span data-stu-id="c35c0-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="c35c0-150">Se você acertar este erro, vá para o Gerenciador do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ela.</span><span class="sxs-lookup"><span data-stu-id="c35c0-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="c35c0-151">Se houver máquinas virtuais conectadas, desconecte-as e exclua a opção de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c35c0-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="c35c0-152">Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="c35c0-153">**Problema: você recebe a seguinte mensagem de erro, "falha do RTCMRAUTH de serviço ao iniciar. Verifique se o serviço não está desabilitado.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c35c0-154">Este problema só se aplica às versões do Cloud Connector anteriores à 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c35c0-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="c35c0-155">A falha ao iniciar também pode ocorrer porque o servidor front-end foi anteriormente com failover (usando o failover do computador).</span><span class="sxs-lookup"><span data-stu-id="c35c0-155">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="c35c0-156">Se esse for o caso, invoque o failback (usando failback de computador).</span><span class="sxs-lookup"><span data-stu-id="c35c0-156">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="c35c0-157">**Resolução:** Esse problema ocorre em um servidor de borda quando o certificado de autoridade de certificação raiz ou o certificado de autoridade de certificação intermediário não é confiável para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c35c0-157">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="c35c0-158">Mesmo que o certificado externo possa ser importado, mas a cadeia de certificados seja quebrada.</span><span class="sxs-lookup"><span data-stu-id="c35c0-158">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="c35c0-159">Sob esta condição, o serviço RTCMRAUTH e/ou RTCSRV não pode ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="c35c0-159">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="c35c0-160">Importe o certificado de autoridade de certificação raiz e todos os certificados de autoridade de certificação intermediários do seu certificado externo manualmente para o servidor de borda e reinicie o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c35c0-160">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="c35c0-161">Após ver os serviços RTCMRAUTH e RTCSRV iniciados no servidor de borda, volte ao servidor host, inicie um console do PowerShell como administrador e execute o cmdlet a seguir para mudar para a nova implantação:</span><span class="sxs-lookup"><span data-stu-id="c35c0-161">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="c35c0-162">**Problema: o servidor host foi reiniciado quando as atualizações do Windows foram aplicadas, e as chamadas atendidas pelo servidor estão falhando.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="c35c0-163">**Resolução:** Se você implantou um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a mover uma máquina host (instância de implantação) para ou para a topologia atual quando você verifica e instala o Windows Update manualmente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="c35c0-164">Use as etapas a seguir para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="c35c0-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="c35c0-165">No servidor host, inicie um console do PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="c35c0-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="c35c0-166">Verifique se há atualizações e instale as que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c35c0-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="c35c0-167">No console do PowerShell, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c35c0-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="c35c0-168">**Problema: quando uma chamada é feita de um cliente do Skype for Business usando um número PSTN, a chamada não pode ser escalonada para uma conferência por meio de um convite a outro número PSTN.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="c35c0-169">**Resolução:** Para resolver esse problema, confira [definir as configurações do servidor de mediação híbrida online](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="c35c0-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="c35c0-170">**Problema: uma mensagem de aviso é exibida sobre o Windows Update quando você está instalando o servidor do Active Directory-"A atualização automática do Windows não está habilitada. Para garantir que sua função ou recurso instalado recentemente seja atualizado automaticamente, ative o Windows Update. "**</span><span class="sxs-lookup"><span data-stu-id="c35c0-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="c35c0-171">**Resolução:** Inicie uma sessão do PowerShell remoto do locatário usando as credenciais de administrador de locatário do Skype for Business e execute o seguinte cmdlet para verificar a configuração do _EnableAutoUpdate_ do seu site:</span><span class="sxs-lookup"><span data-stu-id="c35c0-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="c35c0-172">Se _EnableAutoUpdate_ estiver definido como **true**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement tratará do download e instalando as atualizações do Windows para as máquinas virtuais e o servidor host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="c35c0-173">Se _EnableAutoUpdate_ estiver definido como **false**, execute o cmdlet a seguir para defini-lo como **true**.</span><span class="sxs-lookup"><span data-stu-id="c35c0-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="c35c0-174">Como alternativa, você pode verificar e instalar as atualizações manualmente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="c35c0-175">Confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="c35c0-175">See the next section.</span></span>
    
- <span data-ttu-id="c35c0-176">**Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque o seu servidor de entrada/configuração existente \< SiteName ou dispositivo de mediador ou o endereço IP do servidor de mediação estão \> \< \> \< \> \< \> em conflito com os dispositivos existentes. Remova o dispositivo de conflito ou atualize as informações de entrada/configuração e registre-se novamente. ' ao executar Register-CcAppliance para registrar o dispositivo atual em modo online.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="c35c0-177">**Resolução:** Os valores para o \< appliancename \> , o \< FQDN do servidor de mediação \> e o \< endereço IP do servidor de mediação \> devem ser exclusivos e usados apenas para um registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c35c0-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="c35c0-178">Por padrão, \< \> o CAName é proveniente do nome do host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="c35c0-179">\<O FQDN do servidor de mediação \> e o \< endereço IP do servidor de mediação \> definidos no arquivo ini de configuração.</span><span class="sxs-lookup"><span data-stu-id="c35c0-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="c35c0-180">Por exemplo, usando (Appliancename = MyserverNew, FQDN do servidor de mediação = MS. contoso. com, endereço IP do servidor de mediação = 10.10.10.10) a ser registrado em SiteName = meusite, mas, se houver um dispositivo registrado (Appliance = meuservidor, FQDN do servidor de mediação = MS. contoso. com, endereço IP do servidor de mediação = 10.10.10.10)</span><span class="sxs-lookup"><span data-stu-id="c35c0-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="c35c0-181">Primeiro, verifique o arquivo CloudConnector. ini na seção ApplianceRoot Directory.</span><span class="sxs-lookup"><span data-stu-id="c35c0-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="c35c0-182">Você receberá \< \> os valores do SiteName, do \< servidor de mediação do FQDN \> e do \< endereço IP do servidor de mediação \> no arquivo.</span><span class="sxs-lookup"><span data-stu-id="c35c0-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="c35c0-183">\<Appliance \> é o nome do seu servidor host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="c35c0-184">Em segundo lugar, inicie o PowerShell remoto do locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para verificar os dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="c35c0-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="c35c0-185">Após identificar os conflitos, você pode atualizar o arquivo CloudConnector. ini com informações que correspondam ao dispositivo registrado ou cancelar o registro do dispositivo existente para resolver os conflitos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="c35c0-186">**Problema: o cmdlet Get-CcRunningVersion retorna um valor vazio se houver um dispositivo implantado em execução no host.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="c35c0-187">**Resolução:** Isso pode acontecer quando você atualiza do 1.3.4 ou do 1.3.8 para o 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="c35c0-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="c35c0-188">Após a instalação do 1.4.1 de versão com o. msi, você deve executar o `Register-CcAppliance` antes de executar qualquer outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c35c0-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="c35c0-189">`Register-CcAppliance`migrará o arquivo module. ini do%UserProfile%\CloudConnector para o%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c35c0-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="c35c0-190">Se você o tiver perdido, um novo module. ini será criado na pasta%ProgramData%\CloudConnector e substituirá as informações de versão de execução/backup do 1.3.4 ou do 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="c35c0-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="c35c0-191">Compare os arquivos Module. ini na pasta%UserProfile%\CloudConnector e%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="c35c0-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="c35c0-192">Se houver diferenças, exclua o arquivo module. ini no%ProgramData%\CloudConnector e execute novamente `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="c35c0-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="c35c0-193">Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.</span><span class="sxs-lookup"><span data-stu-id="c35c0-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="c35c0-194">**Problema: depois de executar o cmdlet switch-CcVersion para alternar para uma versão antiga diferente da versão atual do script, não há suporte para alta disponibilidade para esta versão antiga.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="c35c0-195">**Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c35c0-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="c35c0-196">Sua versão atual do script, que pode ser determinada executando `Get-CcVersion` o e a versão em execução, que pode ser determinada pela execução `Get-CcRunningVersion` são ambos 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="c35c0-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="c35c0-197">No momento, se você executar `Switch-CcVersion` o para mudar a versão em execução de volta para o 1.4.1, não haverá suporte de alta disponibilidade para essa versão antiga.</span><span class="sxs-lookup"><span data-stu-id="c35c0-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="c35c0-198">Para obter suporte completo à alta disponibilidade, volte para o 1.4.2, de modo que a versão em execução e a versão do script sejam as mesmas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-198">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="c35c0-199">Se você estiver tendo problemas com sua implantação de 1.4.2, desinstale e reinstale-o assim que possível.</span><span class="sxs-lookup"><span data-stu-id="c35c0-199">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="c35c0-200">**Problema: os certificados da autoridade de certificação ou os certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e servidor de borda estão prestes a expirar ou estão comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="c35c0-201">**Resolução:** Os certificados de autoridade de certificação do Skype for Business são válidos por cinco anos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-201">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="c35c0-202">Os certificados internos emitidos para o repositório de gerenciamento central, o servidor de mediação e o servidor de borda são válidos por dois anos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-202">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c35c0-203">No Cloud Connector versão 2,0 e posterior, o cmdlet Renew-CcServerCertificate mudou para Update-CcServerCertificate e o cmdlet Renew-CcCACertificate mudou para Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="c35c0-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="c35c0-204">Se os certificados internos emitidos para o repositório de gerenciamento central, servidor de mediação e servidor de borda estiverem prestes a expirar ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="c35c0-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c35c0-205">Se os certificados da autoridade de certificação estiverem prestes a expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="c35c0-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="c35c0-206">**Se os certificados da autoridade de certificação estiverem comprometidos e houver apenas um dispositivo no site,** execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="c35c0-207">Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar o dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c35c0-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="c35c0-208">Execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="c35c0-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="c35c0-209">Para versões do Cloud Connector antes de 2,0:</span><span class="sxs-lookup"><span data-stu-id="c35c0-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="c35c0-210">Ou para o Cloud Connector versão 2,0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="c35c0-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="c35c0-211">Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate do dispositivo e instale o certificado exportado nos seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="c35c0-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c35c0-212">Você também pode ser solicitado a emitir novamente o certificado no seu gateway.</span><span class="sxs-lookup"><span data-stu-id="c35c0-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="c35c0-213">Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c35c0-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="c35c0-214">**Se os certificados da autoridade de certificação estiverem comprometidos e houver vários dispositivos no site,** execute as seguintes etapas sequenciais em cada dispositivo no site.</span><span class="sxs-lookup"><span data-stu-id="c35c0-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="c35c0-215">A Microsoft recomenda que você execute estas etapas durante horários que não sejam de pico.</span><span class="sxs-lookup"><span data-stu-id="c35c0-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="c35c0-216">No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da AC no \< diretório SiteRoot \></span><span class="sxs-lookup"><span data-stu-id="c35c0-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="c35c0-217">Execute o cmdlet Enter-CcUpdate para esvaziar os serviços e colocar cada dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c35c0-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="c35c0-218">No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor interno:</span><span class="sxs-lookup"><span data-stu-id="c35c0-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="c35c0-219">Para versões do Cloud Connector antes de 2,0:</span><span class="sxs-lookup"><span data-stu-id="c35c0-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="c35c0-220">Ou para o Cloud Connector versão 2,0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="c35c0-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="c35c0-221">No primeiro dispositivo, execute o cmdlet a seguir para fazer backup dos arquivos da CA na \< \> pasta SiteRoot</span><span class="sxs-lookup"><span data-stu-id="c35c0-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="c35c0-222">Em todos os outros dispositivos do mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os dispositivos usem o mesmo certificado raiz e, em seguida, solicite novos certificados.</span><span class="sxs-lookup"><span data-stu-id="c35c0-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="c35c0-223">Se o TLS for usado entre o gateway e o servidor de mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e, em seguida, instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="c35c0-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="c35c0-224">Você também pode ser solicitado a emitir novamente o certificado no seu gateway.</span><span class="sxs-lookup"><span data-stu-id="c35c0-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="c35c0-225">Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="c35c0-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="c35c0-226">**Problema: você recebe a seguinte mensagem de erro no log do serviço de gerenciamento do Cloud Connector, "C:\Arquivos de Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService erro: 0: exceção inesperada ao relatar o status para online: System. Management. Automation. CmdletInvocationException: falha de logon para o \< administrador de locatário global do usuário \> . Crie um novo objeto Credential, certificando-se de que você tenha usado o nome de usuário e a senha corretos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="c35c0-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="c35c0-227">**Resolução:** As credenciais de administrador de locatário global do Microsoft 365 ou do Office 365 foram alteradas desde que o dispositivo do Cloud Connector foi registrado.</span><span class="sxs-lookup"><span data-stu-id="c35c0-227">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="c35c0-228">Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, execute o seguinte no PowerShell do administrador no dispositivo host:</span><span class="sxs-lookup"><span data-stu-id="c35c0-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="c35c0-229">**Problema: depois de alterar a senha da conta do servidor host que você usou para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString: a chave não é válida para uso no estado especificado." no%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou executando o cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="c35c0-230">**Resolução:** Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".</span><span class="sxs-lookup"><span data-stu-id="c35c0-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="c35c0-231">Quando a senha no servidor host for alterada, será necessário atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="c35c0-232">**Se você estiver executando a versão 1.4.2 do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="c35c0-233">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="c35c0-234">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".</span><span class="sxs-lookup"><span data-stu-id="c35c0-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="c35c0-235">Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="c35c0-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="c35c0-236">Insira as mesmas senhas que você inseriu anteriormente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c35c0-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="c35c0-237">**Se você estiver executando a versão 2,0 ou posterior do Cloud Connector,** regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="c35c0-238">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="c35c0-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="c35c0-239">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".</span><span class="sxs-lookup"><span data-stu-id="c35c0-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="c35c0-240">Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="c35c0-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="c35c0-241">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector, use a senha VMAdmin para a senha do CceService quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="c35c0-241">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="c35c0-242">Insira a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector para todas as outras contas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-242">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="c35c0-243">Se o arquivo de senha em cache foi gerado com a versão 1.4.2 do Cloud Connector e as senhas do DomainAdmin e do VMAdmin forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="c35c0-244">Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c35c0-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="c35c0-245">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="c35c0-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="c35c0-246">Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="c35c0-247">Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2,0 ou posterior, por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService.</span><span class="sxs-lookup"><span data-stu-id="c35c0-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="c35c0-248">Se você alterou as senhas do DomainAdmin e do VMAdmin, deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="c35c0-249">Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c35c0-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c35c0-250">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="c35c0-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c35c0-251">Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="c35c0-252">Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c35c0-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="c35c0-253">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="c35c0-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="c35c0-254">Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin usada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="c35c0-255">**Problema: com o Cloud Connector versão 2,1 e posterior, ao executar o Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "para cada objeto: a propriedade ' Common ' não pode ser encontrada neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**</span><span class="sxs-lookup"><span data-stu-id="c35c0-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="c35c0-256">**Resolução:** O Cloud Connector 2,1 e posterior requer o .NET Framework 4.6.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c35c0-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="c35c0-257">Atualize o .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute novamente o (s) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c35c0-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="c35c0-258">**Problema: com o Cloud Connector Edition 2,1, ao executar install-CcAppliance, você recebe uma mensagem de erro como: "falha ao instalar nova instância com o erro: não é possível definir" State "porque somente cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNodes"**</span><span class="sxs-lookup"><span data-stu-id="c35c0-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="c35c0-259">**Resolução:** No Cloudconnector. ini, na seção [comum], adicione a configuração "estado" da seguinte maneira: CountryCode = US state = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="c35c0-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="c35c0-260">Não é obrigatório para que a linha "State" tenha valor, mas a linha "State" não pode ser removida do arquivo Cloudconnector. ini.</span><span class="sxs-lookup"><span data-stu-id="c35c0-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="c35c0-261">**Problema: você recebe a seguinte mensagem de erro "Dismount-WindowsImage: falha de Dismount-WindowsImage. Código de erro = 0xc1550115 "ao instalar ou atualizar o Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="c35c0-262">**Resolução:** Inicie um console do PowerShell como administrador, execute "DISM-Cleanup-wim" ".</span><span class="sxs-lookup"><span data-stu-id="c35c0-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="c35c0-263">Isso limpará todas as imagens do problemáticas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-263">This will clean up all troubled images.</span></span> <span data-ttu-id="c35c0-264">Execute install-CcAppliance novamente ou espere que os bits sejam atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="c35c0-265">**Problema: falha na implantação do primeiro dispositivo do Cloud Connector em um ambiente de alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="c35c0-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="c35c0-266">**Resolução:** As etapas que você executar dependem do motivo pelo qual a implantação falhou:</span><span class="sxs-lookup"><span data-stu-id="c35c0-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="c35c0-267">Se o primeiro dispositivo do Cloud Connector falhar e você não puder determinar o motivo da falha, você deverá instalar o dispositivo novamente até que a implantação seja bem-sucedida e, em seguida, instalar os outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c35c0-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="c35c0-268">Se o primeiro dispositivo do Cloud Connector falhar com um problema secundário, como um problema de certificado externo, você poderá corrigir o problema sem precisar reinstalar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c35c0-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="c35c0-269">Você pode usar o PowerShell remoto do locatário para marcar a implantação com êxito da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="c35c0-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="c35c0-270">(Você também pode usar as etapas a seguir se a primeira implantação tiver sido bem-sucedida, mas, por algum motivo, o Cloud Connector não conseguir relatar a implantação como um sucesso.)</span><span class="sxs-lookup"><span data-stu-id="c35c0-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="c35c0-271">Para obter a identidade (GUID) do primeiro dispositivo do Cloud Connector, execute o cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="c35c0-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="c35c0-272">Para marcar o dispositivo como implantado com êxito, execute o set-CsCceApplianceDeploymentStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c35c0-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="c35c0-273">**Problema: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou nas máquinas virtuais.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="c35c0-274">**Resolução:** Recomendamos que você aproveite as atualizações automatizadas de so fornecidas pelo Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c35c0-274">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="c35c0-275">Depois que um dispositivo é registrado para o gerenciamento online e a atualização de so automática está habilitada, o servidor host e as máquinas virtuais verificam e instalam as atualizações do Windows automaticamente, de acordo com as configurações da janela de tempo de atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c35c0-275">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="c35c0-276">Se você precisar verificar e instalar as atualizações do Windows manualmente, siga as etapas desta seção que se aplicam ao seu tipo de implantação.</span><span class="sxs-lookup"><span data-stu-id="c35c0-276">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="c35c0-277">Você deve planejar a atualização do servidor host e das máquinas virtuais em execução no mesmo momento para minimizar a quantidade de tempo de inatividade necessária para as atualizações.</span><span class="sxs-lookup"><span data-stu-id="c35c0-277">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="c35c0-278">Se preferir, você pode usar um servidor WSUS (Windows Server Update Services) para fornecer atualizações para os servidores do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c35c0-278">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="c35c0-279">Apenas certifique-se de configurar o Windows Update para **não** instalar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-279">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="c35c0-280">Para obter informações sobre como atualizar manualmente sua implantação do Cloud Connector, consulte a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="c35c0-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="c35c0-281">**Problema: quando as atualizações do Cloud Connector para um novo Build, os cmdlets do Cloud Connector não são atualizados.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="c35c0-282">Às vezes, isso ocorre quando uma janela do PowerShell é deixada aberta quando ocorre a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="c35c0-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="c35c0-283">**Resolução:** Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c35c0-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="c35c0-284">Feche o PowerShell no dispositivo do Cloud Connector e reabra o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c35c0-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="c35c0-285">Ou, você pode executar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="c35c0-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="c35c0-286">**Problema: "o termo" Stop-CsWindowsService "não é reconhecido como o nome de um cmdlet, de função, de um arquivo de script ou de um programa operável." erro ao tentar executar o cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="c35c0-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="c35c0-287">**Resolução:** Exclua o arquivo $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="c35c0-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="c35c0-288">O PowerShell cria esse arquivo como um cache de cmdlets de módulos que ele encontra, de forma que não seja necessário analisar novamente todos os módulos, sempre que isso tornaria as coisas muito lentas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="c35c0-289">Provavelmente, houve alguma corrupção de arquivo que forneciam resultados enganosos para o PowerShell quando ele estava lendo novamente desse cache.</span><span class="sxs-lookup"><span data-stu-id="c35c0-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="c35c0-290">**Problema: "Import-Module CloudConnector" gera o erro "Import-Module: o módulo especificado" CloudConnector "não foi carregado porque nenhum arquivo de módulo válido foi encontrado em nenhum diretório de módulo"**</span><span class="sxs-lookup"><span data-stu-id="c35c0-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="c35c0-291">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="c35c0-291">**Resolution:**</span></span>
    - <span data-ttu-id="c35c0-292">Validar que o módulo CloudConnector existe em c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="c35c0-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="c35c0-293">Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazena o caminho para os locais dos módulos pode ser alterada:</span><span class="sxs-lookup"><span data-stu-id="c35c0-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="c35c0-294">a.</span><span class="sxs-lookup"><span data-stu-id="c35c0-294">a.</span></span> <span data-ttu-id="c35c0-295">Alteração temporária: Inicie o PowerShell como administrador e execute o seguinte comando: $env:P SModulePath = $env:P SModulePath + "; C:\Arquivos de Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="c35c0-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="c35c0-296">b.</span><span class="sxs-lookup"><span data-stu-id="c35c0-296">b.</span></span> <span data-ttu-id="c35c0-297">Para uma alteração persistente, inicie o PowerShell como administrador e execute os seguintes comandos, um por um: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Arquivos de Files\WindowsPowerShell\Modules "," Machine ")</span><span class="sxs-lookup"><span data-stu-id="c35c0-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="c35c0-298">Instalar as atualizações do Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="c35c0-298">Install Windows updates manually</span></span>

<span data-ttu-id="c35c0-299">Se não quiser usar as atualizações automáticas em seu ambiente, siga estas etapas para verificar e aplicar as atualizações do Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="c35c0-300">Verificar e instalar as atualizações do Windows pode exigir uma reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="c35c0-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="c35c0-301">Quando um servidor host está sendo reiniciado, os usuários não poderão usar o Cloud Connector para fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="c35c0-302">Você pode verificar e instalar as atualizações manualmente para controlar quando as atualizações ocorrerem e, em seguida, reiniciar as máquinas conforme necessário durante os horários em que você optar por evitar a interrupção de serviços.</span><span class="sxs-lookup"><span data-stu-id="c35c0-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="c35c0-303">Para verificar as atualizações manualmente, conecte-se a cada servidor host e abra o **painel de controle**.</span><span class="sxs-lookup"><span data-stu-id="c35c0-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="c35c0-304">Selecione **sistema e segurança \> Windows Update**e gerencie as atualizações e as reinicializações do servidor conforme apropriado para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c35c0-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="c35c0-305">Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **painel de controle**.</span><span class="sxs-lookup"><span data-stu-id="c35c0-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="c35c0-306">Selecione **sistema e segurança \> Windows Update**e configure as atualizações e as reinicializações do servidor conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="c35c0-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="c35c0-307">Se houver mais de um dispositivo no site, a instância que está sendo atualizada e reiniciada não poderá ser acessada pelos usuários durante as atualizações.</span><span class="sxs-lookup"><span data-stu-id="c35c0-307">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="c35c0-308">Os usuários se conectarão a outras instâncias na implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business sejam iniciados nas máquinas virtuais depois que as atualizações forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="c35c0-308">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="c35c0-309">Para evitar qualquer interrupção em potencial para o serviço, você pode remover a instância da alta disponibilidade enquanto aplica as atualizações e, em seguida, restaurá-la ao concluir.</span><span class="sxs-lookup"><span data-stu-id="c35c0-309">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="c35c0-310">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="c35c0-310">To do so:</span></span>
    
1. <span data-ttu-id="c35c0-311">Em cada servidor host, abra um console do PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c35c0-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="c35c0-312">Remova a instância da alta disponibilidade com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c35c0-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="c35c0-313">Siga as etapas para uma única instância para aplicar manualmente as atualizações e reiniciar a máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="c35c0-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="c35c0-314">Defina a instância de volta para HA com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c35c0-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="c35c0-315">Para implantações de vários sites, siga as etapas para um único site para cada site na implantação, aplicando atualizações a um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="c35c0-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="c35c0-316">Dicas ao instalar o software antivírus na máquina host do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c35c0-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="c35c0-317">Se for necessário instalar o software antivírus na máquina host do Cloud Connector, você precisará adicionar as seguintes exclusões:</span><span class="sxs-lookup"><span data-stu-id="c35c0-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="c35c0-318">Diretório de dispositivo local em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="c35c0-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="c35c0-319">Diretório de sites remotos em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="c35c0-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="c35c0-320">Diretório de sites locais no computador hospeda a pasta raiz do site compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c35c0-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="c35c0-321">%ProgramFiles%\Skype para o Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c35c0-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="c35c0-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c35c0-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="c35c0-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="c35c0-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="c35c0-324">O processo Microsoft. RTC. CCE. ManagementService. exe.</span><span class="sxs-lookup"><span data-stu-id="c35c0-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
