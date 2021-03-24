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
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094819"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="4ebe3-103">Solução de problemas de implantação do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ebe3-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="4ebe3-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4ebe3-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="4ebe3-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="4ebe3-106">Solucionar problemas de implantação do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="4ebe3-107">Este tópico descreve soluções para problemas comuns com implantações do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="4ebe3-108">Se você estiver enfrentando problemas com chamadas de e para a PSTN (Rede Telefônica Pública Comucionada), você pode investigar seguindo as soluções descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="4ebe3-109">O Cloud Connector fornece mecanismos integrados para resolver automaticamente alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="4ebe3-110">Um processo de detecção automática procura possíveis problemas com os dispositivos do Cloud Connector e, se possível, toma medidas corretivas para resolver esses problemas sem a necessidade de intervenção do administrador.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="4ebe3-111">O processo de detecção funciona da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="4ebe3-112">**Sequência de detecção:** O serviço de Gerenciamento do Cloud Connector executa um processo a cada 60 segundos para detectar se um dispositivo está ino mesmo.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="4ebe3-113">No Cloud Connector versão 2.0 e posterior, o processo de detecção usa a opção Skype for Business Corpnet para fazer conexões do PowerShell com os máquinas do Cloud Connector; para versões anteriores a 2.0, o processo de detecção usa a opção de gerenciamento do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ebe3-114">Para que a recuperação automática seja bem-sucedida, deve haver conectividade de rede entre o host e as máquinas virtuais por meio da opção de rede do host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="4ebe3-115">Verifique a conectividade de rede para garantir que a detecção e a recuperação automática possam ser bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="4ebe3-116">**Monitoramento:** Os seguintes serviços são monitorados no Cloud Connector versão 2.0 e posterior:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="4ebe3-117">As Máquinas Virtuais não estão conectadas aos comutadores virtuais corporativos ou da Internet do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ebe3-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="4ebe3-118">As Máquinas Virtuais estão em um status salvo ou interrompido</span><span class="sxs-lookup"><span data-stu-id="4ebe3-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="4ebe3-119">Serviços do Servidor de Gerenciamento Central: RÉPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="4ebe3-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="4ebe3-120">Serviços do Servidor de Mediação: RÉPLICA, RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="4ebe3-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="4ebe3-121">Serviços do Servidor de Borda: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="4ebe3-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="4ebe3-122">As regras de firewall de entrada estão desabilitadas para CS RTCSRV no servidor de Borda, CS RTCMEDSRV no servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="4ebe3-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="4ebe3-123">No Cloud Connector versão 1.4.2, somente os seguintes serviços são monitorados:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="4ebe3-124">Serviços do Servidor de Mediação: RTCSRV e MEDSVC</span><span class="sxs-lookup"><span data-stu-id="4ebe3-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="4ebe3-125">Serviço de Servidor de Borda: RTCSRV</span><span class="sxs-lookup"><span data-stu-id="4ebe3-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="4ebe3-126">**Processo de recuperação:** Se algum serviço monitorado estiver inosse, um dispositivo será marcado para baixo e os serviços serão interrompidos e marcados manualmente até que todos os problemas possam ser resolvidos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="4ebe3-127">Isso impedirá que as chamadas roteem para um dispositivo que possa causar falhas de chamada.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="4ebe3-128">O serviço de Gerenciamento do Cloud Connector repetirá a recuperação automática da seguinte forma</span><span class="sxs-lookup"><span data-stu-id="4ebe3-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="4ebe3-129">O intervalo inicial de nova tentativa é a cada dez segundos com um intervalo máximo de uma hora.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="4ebe3-130">Para as três primeiras tentativas de recuperação, o tempo de intervalo é de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="4ebe3-131">A partir da quarta tentativa, o tempo de intervalo aumenta duas vezes o tempo de intervalo anterior.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="4ebe3-132">Por exemplo, a quarta tentativa ocorrerá em 20 segundos, a quinta em 40 segundos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="4ebe3-133">Quando o tempo máximo de intervalo de uma hora é atingido, as recuperações continuarão uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="4ebe3-134">Quando a recuperação é bem-sucedida, as contagens de intervalo e de tentativa são definidas como seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="4ebe3-135">Se o serviço de Gerenciamento for reiniciado, as contagens de intervalo e de nova tentativa serão redefinidas para seus valores iniciais.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="4ebe3-136">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="4ebe3-136">Troubleshooting</span></span>

<span data-ttu-id="4ebe3-137">A seguir estão soluções para problemas comumente encontrados:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="4ebe3-138">**Problema: a implantação falha ou para de responder ao executar os scripts de implantação. Depois de fazer logon em cada VM, o endereço IP está ausente ou incorreto para a NIC Gerenciamento/Interna/Externa.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="4ebe3-139">**Resolução:** Esse problema não pode ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="4ebe3-140">Os NICs não podem ser adicionados a VMs enquanto eles estão em execução.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="4ebe3-141">Desligue e remova essas VMs no gerenciador hyper-v e execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="4ebe3-142">**Problema: depois que o Servidor do Active Directory e a floresta são instalados, o Servidor CMS e/ou Servidor de Mediação não ingressaram no domínio corretamente.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="4ebe3-143">**Resolução:** Para resolver esse problema, tome as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="4ebe3-144">Faça logoff no Servidor do Active Directory e verifique se o domínio foi criado corretamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="4ebe3-145">Faça logon no SERVIDOR CMS/Mediação e verifique se, na NIC da corpnet, um endereço IP válido está atribuído e se o IP estático válido e DNS está configurado como o endereço IP do servidor AD.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="4ebe3-146">Faça logon no SERVIDOR CMS/Mediação e abra um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="4ebe3-147">Certifique-se de que você pode pingar o FQDN e o endereço IP do Servidor do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="4ebe3-148">Se você não puder, pode haver um conflito de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="4ebe3-149">Tente atribuir um novo IP para o Active Directory e atualize o DNS no servidor CMS/Mediação de acordo.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="4ebe3-150">**Problema: Você recebe a seguinte mensagem de erro, "Remove-VMSwitch : Falhou ao remover a opção Ethernet virtual. A opção virtual 'Cloud Connector Management Switch' não pode ser excluída porque está sendo usada pela execução de máquinas virtuais ou atribuída a pools filho."**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="4ebe3-151">**Resolução:** O "Cloud Connector Management Switch" não foi excluído após a implantação.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="4ebe3-152">Se você tiver atingido esse erro, vá até o gerente do Hyper-v e verifique se ainda não há uma máquina virtual conectada a ela.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="4ebe3-153">Se ainda houver máquinas virtuais conectadas, desconecte-as e exclua a opção de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="4ebe3-154">Se a opção de gerenciamento ainda não puder ser excluída, reinicie o servidor host e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="4ebe3-155">**Problema: Você recebe a seguinte mensagem de erro: "Falha ao iniciar o serviço RTCMRAUTH. Verifique se o serviço não está desabilitado."**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ebe3-156">Esse problema só se aplica a versões do Cloud Connector anteriores a 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="4ebe3-157">A falha ao iniciar também pode ser porque esse servidor Front-End foi anteriormente reprovado (usando o fail over do computador).</span><span class="sxs-lookup"><span data-stu-id="4ebe3-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="4ebe3-158">Se esse for o caso, invoque fail-back (usando o fail back do computador).</span><span class="sxs-lookup"><span data-stu-id="4ebe3-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="4ebe3-159">**Resolução:** Esse problema acontece em um Servidor de Borda quando o certificado de AC raiz ou certificado de AC intermediário não é confiável pelo Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="4ebe3-160">Mesmo que o certificado externo possa ser importado, mas a cadeia de certificados estiver quebrada.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="4ebe3-161">Nessa condição, o serviço RTCMRAUTH e/ou RTCSRV não pode iniciar.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="4ebe3-162">Importe o certificado de AC raiz e todos os certificados ca intermediários do certificado externo manualmente para o Servidor de Borda e reinicie o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="4ebe3-163">Depois de ver os serviços RTCMRAUTH e RTCSRV iniciados no Servidor de Borda, volte para o servidor host, iniciar um console do PowerShell como administrador e executar o seguinte cmdlet para alternar para a nova implantação:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="4ebe3-164">**Problema: o servidor host foi reiniciado quando as atualizações do Windows foram aplicadas e as chamadas a serviço do servidor estão falhando.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="4ebe3-165">**Resolução:** Se você implantou um ambiente de alta disponibilidade, a Microsoft fornece um cmdlet para ajudar a mover uma máquina host (instância de implantação) para dentro ou para fora da topologia atual ao verificar e instalar a atualização do Windows manualmente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="4ebe3-166">Use as etapas a seguir para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="4ebe3-167">No servidor host, inicie um console do PowerShell como administrador e execute:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="4ebe3-168">Verifique se há atualizações e instale todas as que estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="4ebe3-169">No console do PowerShell, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="4ebe3-170">**Problema: quando uma chamada é feita de um cliente do Skype for Business usando um número PSTN, a chamada não pode ser escalonada para uma conferência convidando outro número PSTN.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="4ebe3-171">**Resolução:** Para resolver esse problema, consulte [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="4ebe3-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="4ebe3-172">**Problema: uma mensagem de aviso é exibida sobre o Windows Update quando você está instalando o servidor do Active Directory - "A atualização automática do Windows não está habilitada. Para garantir que sua função ou recurso recém-instalado seja atualizado automaticamente, ata o Windows Update."**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="4ebe3-173">**Resolução:** Iniciar uma sessão do Tenant Remote PowerShell usando credenciais de administrador de locatários do Skype for Business e execute o seguinte cmdlet para verificar a configuração _EnableAutoUpdate_ do seu site:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="4ebe3-174">Se  _EnableAutoUpdate_ estiver definido como **True**, você poderá ignorar com segurança essa mensagem de aviso porque o serviço CCEManagement tratará do download e da instalação de atualizações do Windows para máquinas virtuais e para o servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="4ebe3-175">Se  _EnableAutoUpdate_ for definido como **False**, execute o seguinte cmdlet para defini-lo como **True**.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="4ebe3-176">Como alternativa, você pode verificar manualmente e instalar atualizações.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="4ebe3-177">Confira a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-177">See the next section.</span></span>
    
- <span data-ttu-id="4ebe3-178">**Problema: você recebe uma mensagem de erro: não é possível registrar o dispositivo porque sua entrada/configuração atual ou ou conflitos com os \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> dispositivos existentes. Remova o dispositivo de conflito ou atualize suas informações de entrada/configuração e registre-se novamente. ' ao executar Register-CcAppliance para registrar o dispositivo atual online.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="4ebe3-179">**Resolução:** Valores para \<ApplianceName\> o , e devem ser \<Mediation Server FQDN\> \<Mediation Server IP Address\> exclusivos e usados apenas para um registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="4ebe3-180">Por padrão, \<ApplianceName\> vem do nome do host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="4ebe3-181">\<Mediation Server FQDN\> e \<Mediation Server IP Address\> definido no arquivo de configuração ini.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="4ebe3-182">Por exemplo, usando (ApplianceName= MyserverNew, FQDN=ms.contoso.com, Endereço IP do Servidor de Mediação=10.10.10.10) para registrar-se em SiteName=MySite, mas se houver um dispositivo registrado (ApplianceName= Myserver, Servidor de Mediação FQDN=ms.contoso.com, Endereço IP do Servidor de Mediação=10.10.10.10), você terá o conflito.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="4ebe3-183">Primeiro, verifique seu arquivo CloudConnector.ini na seção Diretório ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="4ebe3-184">Você receberá \<SiteName\> valores e valores no \<Mediation Server FQDN\> \<Mediation Server IP Address\> arquivo.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="4ebe3-185">\<ApplianceName\> é o nome do servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="4ebe3-186">Em segundo lugar, iniciar o PowerShell Remoto do Locatário usando suas credenciais de administrador de locatários do Skype for Business e, em seguida, execute o cmdlet a seguir para verificar os dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="4ebe3-187">Depois de identificar quaisquer conflitos, você pode atualizar seu arquivo CloudConnector.ini com informações que corresponde ao dispositivo registrado ou não registrar o dispositivo existente para resolver os conflitos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="4ebe3-188">**Problema: o Get-CcRunningVersion cmdlet retorna um valor vazio se houver um dispositivo implantado em execução no host.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="4ebe3-189">**Resolução:** Isso pode acontecer quando você atualiza de 1.3.4 ou 1.3.8 para 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="4ebe3-190">Depois de instalar a versão 1.4.1 com o .msi, você deve executar antes de executar `Register-CcAppliance` qualquer outro cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="4ebe3-191">`Register-CcAppliance` migrará o arquivo module.ini de %UserProfile%\CloudConnector para %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="4ebe3-192">Se você não tiver perdido, um novo module.ini será criado na pasta %ProgramData%\CloudConnector e substituirá as informações de versão de execução/backup por 1.3.4 ou 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="4ebe3-193">Compare module.ini arquivos em %UserProfile%\CloudConnector e %ProgramData%\Pasta CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="4ebe3-194">Se houver diferenças, exclua o arquivo module.ini em %ProgramData%\CloudConnector e reprise  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="4ebe3-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="4ebe3-195">Você também pode modificar o arquivo manualmente para a versão correta de execução e backup.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="4ebe3-196">**Problema: depois de executar o cmdlet Switch-CcVersion para alternar para uma versão antiga que é diferente da versão de script atual, não há suporte para Alta Disponibilidade para essa versão antiga.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="4ebe3-197">**Resolução:** Por exemplo, você atualizou de 1.4.1 para 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="4ebe3-198">Sua versão de script atual, que pode ser determinada executando e sua versão em execução, que pode ser determinada pela execução são `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="4ebe3-199">Neste momento, se você executar para alternar a versão em execução de volta para 1.4.1, não haverá suporte para Alta Disponibilidade para `Switch-CcVersion` essa versão antiga.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="4ebe3-200">Para obter suporte completo a Alta Disponibilidade, alternar de volta para 1.4.2, para que a versão em execução e a versão de script sejam as mesmas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="4ebe3-201">Se você estiver enfrentando problemas com sua implantação 1.4.2, desinstale e reinstale-o assim que possível.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="4ebe3-202">**Problema: certificados de autoridade de certificado ou certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos de expirar ou estão comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="4ebe3-203">**Resolução:** Os certificados de autoridade de certificação do Skype for Business são válidos por cinco anos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="4ebe3-204">Os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda são válidos por dois anos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ebe3-205">No Cloud Connector versão 2.0 e posterior, o cmdlet Renew-CcServerCertificate foi alterado para Update-CcServerCertificate e o cmdlet Renew-CcCACertificate foi alterado para Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="4ebe3-206">Se os certificados internos emitidos para o Armazenamento de Gerenciamento Central, o Servidor de Mediação e o Servidor de Borda estão próximos da expiração ou comprometidos, execute o cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="4ebe3-207">Se os certificados de autoridade de certificação estão próximos de expirar, execute o cmdlet Renew-CcCACertificate ou Update-CcCACertificate para renovar seus certificados.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="4ebe3-208">**Se os certificados de autoridade de** certificação estão comprometidos e há apenas um dispositivo no site, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="4ebe3-209">Execute o cmdlet Enter-CcUpdate para drenar os serviços e colocar o dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="4ebe3-210">Execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="4ebe3-211">Para versões do Cloud Connector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="4ebe3-212">Ou para a versão 2.0 do Cloud Connector e posterior:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="4ebe3-213">Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate do dispositivo e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="4ebe3-214">Você também pode ser obrigado a reemissão do certificado em seu gateway.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="4ebe3-215">Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="4ebe3-216">**Se os certificados de** autoridade de certificação estão comprometidos e há vários dispositivos no site, execute as etapas sequenciais a seguir em cada dispositivo no site.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="4ebe3-217">A Microsoft recomenda que você execute essas etapas durante os horários de uso que não são de pico.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="4ebe3-218">No primeiro dispositivo, execute o cmdlet Remove-CcCertificationAuthorityFile para limpar os arquivos de backup da CA no \<SiteRoot\> diretório.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="4ebe3-219">Execute o cmdlet Enter-CcUpdate para drenar os serviços e colocar cada dispositivo no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="4ebe3-220">No primeiro dispositivo, execute os seguintes cmdlets para redefinir e criar novos certificados de autoridade de certificação e todos os certificados de servidor internos:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="4ebe3-221">Para versões do Cloud Connector antes de 2.0:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="4ebe3-222">Ou para a versão 2.0 do Cloud Connector e posterior:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="4ebe3-223">No primeiro dispositivo, execute o seguinte cmdlet para fazer o back up dos arquivos ca na \<SiteRoot\> pasta.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="4ebe3-224">Em todos os outros dispositivos no mesmo site, execute os seguintes comandos para consumir os arquivos de backup da CA, para que todos os dispositivos usem o mesmo certificado raiz e solicitem novos certificados.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="4ebe3-225">Se o TLS for usado entre o gateway e o Servidor de Mediação, execute o cmdlet Export-CcRootCertificate de qualquer dispositivo no site e instale o certificado exportado para seus gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="4ebe3-226">Você também pode ser obrigado a reemissão do certificado em seu gateway.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="4ebe3-227">Execute o cmdlet Exit-CcUpdate para iniciar os serviços e sair do modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="4ebe3-228">**Problema: você recebe a seguinte mensagem de erro no Log de Serviço de Gerenciamento do Cloud Connector, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": Erro CceService: 0 : exceção inesperada ao relatar o status para online: System.Management.Automation.CmdletInvocationException: Falha no logon para o usuário \<Global Tenant Admin\> . Crie um novo objeto de credencial, certifique-se de ter usado o nome de usuário e a senha corretos. ---\>**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="4ebe3-229">**Resolução:** As credenciais de administrador global do locatário do Microsoft 365 ou office 365 foram alteradas desde que o dispositivo do Cloud Connector foi registrado.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="4ebe3-230">Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, execute o seguinte do Administrador do PowerShell no dispositivo host:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="4ebe3-231">**Problema: depois de alterar a senha da conta de servidor host usada para a implantação, você recebe a seguinte mensagem de erro: "ConvertTo-SecureString : Chave não válida para uso no estado especificado." em %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou durante a execução do cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="4ebe3-232">**Resolução:** Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="4ebe3-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="4ebe3-233">Quando a senha no servidor host for mudada, você precisará atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="4ebe3-234">**Se você estiver executando o Cloud Connector versão 1.4.2,** regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="4ebe3-235">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="4ebe3-236">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="4ebe3-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="4ebe3-237">Iniciar um console do PowerShell como administrador e executar "Register-CcAppliance -Local" para inserir as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="4ebe3-238">Insira as mesmas senhas inseridas antes para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="4ebe3-239">**Se você estiver executando o Cloud Connector versão 2.0** ou posterior, regenere todas as senhas do Cloud Connector seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="4ebe3-240">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="4ebe3-241">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml" .</span><span class="sxs-lookup"><span data-stu-id="4ebe3-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="4ebe3-242">Iniciar um console do PowerShell como administrador e executar "Register-CcAppliance -Local" para inserir as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="4ebe3-243">Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 1.4.2, use a senha VMAdmin para a senha CceService quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="4ebe3-244">Insira a mesma senha inserida antes para a implantação do Cloud Connector para todas as outras contas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="4ebe3-245">Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 1.4.2 e as senhas DomainAdmin e VMAdmin são diferentes, você deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="4ebe3-246">Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="4ebe3-247">Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="4ebe3-248">Quando solicitado a nova credencial da conta, insira a senha da senha DomainAdmin que você usou antes.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="4ebe3-249">Se o arquivo de senha em cache foi gerado com o Cloud Connector versão 2.0 ou posterior, por padrão, VmAdmin e DomainAdmin usarão a mesma senha que CceService.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="4ebe3-250">Se você tiver alterado as senhas DomainAdmin e VMAdmin, deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="4ebe3-251">Execute Set-CcCredential -AccountType DomainAdmin da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="4ebe3-252">Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="4ebe3-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="4ebe3-253">Quando solicitado a nova credencial da conta, insira a senha da senha DomainAdmin que você usou antes.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="4ebe3-254">Execute Set-CcCredential -AccountType VmAdmin da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="4ebe3-255">Quando solicitado a usar a credencial da conta antiga, insira a credencial usada para a senha do CceService</span><span class="sxs-lookup"><span data-stu-id="4ebe3-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="4ebe3-256">Quando solicitado para a nova credencial da conta, insira a senha da senha VmAdmin que você usou antes.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="4ebe3-257">**Problema: com o Cloud Connector versão 2.1 e posterior, ao executar o Register-CcAppliance ou outros cmdlets no dispositivo, você recebe uma mensagem de erro como: "Para Each-Object : a propriedade 'Common' não pode ser encontrada neste objeto. Verifique se a propriedade existe. Em C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="4ebe3-258">**Resolução:** O Cloud Connector 2.1 e posterior requer .NET Framework 4.6.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="4ebe3-259">Atualize .NET Framework no dispositivo para a versão 4.6.1 ou posterior e execute os cmdlets novamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="4ebe3-260">**Problema: com o Cloud Connector Edition 2.1, ao executar Install-CcAppliance, você recebe uma mensagem de erro como: "Falha ao instalar nova instância com erro: não é possível definir "Estado" porque somente cadeias de caracteres podem ser usadas como valores para definir propriedades XmlNode"**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="4ebe3-261">**Resolução:** Em Cloudconnector.ini, na seção [Comum], adicione a configuração "Estado" abaixo: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="4ebe3-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="4ebe3-262">Não é obrigatório que a linha "State" tenha valor, no entanto, a linha "State" não pode ser removida do arquivo Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="4ebe3-263">**Problema: Você recebe a seguinte mensagem de erro "Dismount-WindowsImage : Dismount-WindowsImage falhou. Código de erro = 0xc1550115" ao instalar ou atualizar o Cloud Connector Edition.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="4ebe3-264">**Resolução:** Iniciar um console do PowerShell como administrador, execute "DISM -Cleanup-Wim'".</span><span class="sxs-lookup"><span data-stu-id="4ebe3-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="4ebe3-265">Isso limpará todas as imagens problemáticas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-265">This will clean up all troubled images.</span></span> <span data-ttu-id="4ebe3-266">Execute Install-CcAppliance ou aguarde que os bits atualizem automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="4ebe3-267">**Problema: Falha na implantação do primeiro dispositivo do Cloud Connector em um ambiente de HA**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="4ebe3-268">**Resolução:** As etapas que você tomar dependem do motivo pelo qual a implantação falhou:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="4ebe3-269">Se o primeiro dispositivo do Cloud Connector falhar e você não puder determinar o motivo da falha, instale o dispositivo novamente até que a implantação seja bem-sucedida e instale os outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="4ebe3-270">Se o primeiro dispositivo do Cloud Connector falhar com um problema secundário, como um problema de certificado externo, talvez seja possível corrigir o problema sem instalar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="4ebe3-271">Em seguida, você pode usar o PowerShell remoto do locatário para marcar a implantação como bem-sucedida da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="4ebe3-272">(Você também pode usar as etapas a seguir se a primeira implantação foi bem-sucedida, mas, por algum motivo, o Cloud Connector não relata a implantação como um sucesso.)</span><span class="sxs-lookup"><span data-stu-id="4ebe3-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="4ebe3-273">Para obter a Identidade (GUID) do primeiro dispositivo do Cloud Connector, execute o cmdlet Get-CsHybridPSTNAppliance de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="4ebe3-274">Para marcar o dispositivo como implantado com êxito, execute o Set-CsCceApplianceDeploymentStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="4ebe3-275">**Problema: você precisa verificar e instalar as atualizações do Windows manualmente no servidor host ou em máquinas virtuais.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="4ebe3-276">**Resolução:** Recomendamos que você aproveite as atualizações automatizadas do sistema operacional fornecidas pelo Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="4ebe3-277">Depois que um dispositivo é registrado para gerenciamento online e a atualização automática do sistema operacional está habilitada, o servidor host e máquinas virtuais verificarão e instalarão as Atualizações do Windows automaticamente de acordo com as configurações da janela de tempo de atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="4ebe3-278">Se você precisar verificar e instalar o Windows Updates manualmente, siga as etapas nesta seção que se aplicam ao seu tipo de implantação.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="4ebe3-279">Você deve planejar a atualização do servidor host e das máquinas virtuais em execução nele ao mesmo tempo para minimizar a quantidade de tempo de inação necessária para as atualizações.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="4ebe3-280">Se preferir, você pode usar um servidor do Windows Server Update Services (WSUS) para fornecer atualizações para servidores do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="4ebe3-281">Basta configurar o Windows Update para não **instalar** automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="4ebe3-282">Para obter informações sobre como atualizar manualmente sua implantação do Cloud Connector, consulte a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="4ebe3-283">**Problema: quando o Cloud Connector é atualizado para uma nova com build, os cmdlets do Cloud Connector não são atualizados.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="4ebe3-284">Isso às vezes acontece se uma janela do PowerShell for deixada aberta quando a atualização automática ocorrer.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="4ebe3-285">**Resolução:** Para carregar os cmdlets atualizados, você pode fazer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="4ebe3-286">Feche o PowerShell no dispositivo do Cloud Connector e reabra o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="4ebe3-287">Ou, você pode executar Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="4ebe3-288">**Problema: "O termo 'Stop-CsWindowsService' não é reconhecido como o nome de um cmdlet, função, arquivo de script ou programa operável." ao tentar executar Enter-CcUpdate cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="4ebe3-289">**Resolução:** Exclua o arquivo $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="4ebe3-290">O PowerShell cria esse arquivo como um cache de cmdlets a partir de módulos que ele encontra para que ele não tenha que analisar todos os módulos sempre, pois isso torna as coisas muito lentas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="4ebe3-291">Provavelmente, houve alguma corrupção de arquivo que forneceu resultados enganosos para o PowerShell quando ele estava lendo de volta desse cache.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="4ebe3-292">**Problema: "Import-Module CloudConnector" gera erro "Import-Module: The specified module "CloudConnector" was not loaded because no valid module file was found in any module directory"**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="4ebe3-293">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="4ebe3-293">**Resolution:**</span></span>
    - <span data-ttu-id="4ebe3-294">Valide se, na verdade, o módulo CloudConnector existe em c:\Arquivos de Programas\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="4ebe3-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="4ebe3-295">Depois de validar que o módulo CloudConnector existe nesse local, a variável de ambiente PSModulePath que armazenará o caminho para os locais dos módulos pode ser alterada:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="4ebe3-296">a.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-296">a.</span></span> <span data-ttu-id="4ebe3-297">Alteração temporária: inicie o Powershell como administrador e execute o seguinte comando: $env:PSModulePath = $env:PSModulePath + "; C:\Arquivos de Programas\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="4ebe3-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="4ebe3-298">b.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-298">b.</span></span> <span data-ttu-id="4ebe3-299">Para alterações persistentes, inicie o PowerShell como administrador e execute os seguintes comandos, um a um: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Arquivos de Programas\WindowsPowerShell\Modules", "Machine")</span><span class="sxs-lookup"><span data-stu-id="4ebe3-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="4ebe3-300">Instalar atualizações do Windows manualmente</span><span class="sxs-lookup"><span data-stu-id="4ebe3-300">Install Windows updates manually</span></span>

<span data-ttu-id="4ebe3-301">Se você não quiser usar atualizações automáticas em seu ambiente, siga estas etapas para verificar manualmente e aplicar atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="4ebe3-302">Verificar e instalar atualizações do Windows pode exigir uma reinicialização do servidor.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="4ebe3-303">Quando um servidor host estiver sendo reiniciado, os usuários não poderão usar o Cloud Connector para fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="4ebe3-304">Você pode verificar manualmente e instalar atualizações para controlar quando as atualizações ocorrem e reiniciar os dispositivos conforme necessário durante os horários que você optar por evitar interrupção dos serviços.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="4ebe3-305">Para verificar manualmente as atualizações, conecte-se a cada servidor host e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="4ebe3-306">Selecione **Sistema e Segurança do Windows \> Update** e, em seguida, gerencie as atualizações e reinicializações do servidor conforme apropriado para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="4ebe3-307">Se houver apenas um dispositivo no site, conecte-se a cada máquina virtual e abra o **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="4ebe3-308">Selecione **Sistema e Segurança do Windows \> Update** e, em seguida, configure as atualizações e reinicializações do servidor conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="4ebe3-309">Se houver mais de um dispositivo no site, a instância que está sendo atualizada e reiniciada não poderá ser acessada pelos usuários durante as atualizações.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="4ebe3-310">Os usuários se conectarão a outras instâncias na implantação até que todas as máquinas virtuais e todos os serviços do Skype for Business comecem nas máquinas virtuais após a conclusão das atualizações.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="4ebe3-311">Para evitar possíveis interrupções no serviço, você pode remover a instância do HA enquanto aplica as atualizações e restaurá-la quando concluída.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="4ebe3-312">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-312">To do so:</span></span>
    
1. <span data-ttu-id="4ebe3-313">Em cada servidor host, abra um console do PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="4ebe3-314">Remova a instância de HA com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="4ebe3-315">Siga as etapas para que uma única instância aplique manualmente as atualizações e reinicie a máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="4ebe3-316">De definir a instância de volta como HA com o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="4ebe3-317">Para implantações de vários sites, siga as etapas de um único site para cada site na implantação, aplicando atualizações a um site por vez.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="4ebe3-318">Dicas ao instalar software antivírus na máquina host do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4ebe3-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="4ebe3-319">Se você precisar instalar software antivírus na máquina host do Cloud Connector, será necessário adicionar as seguintes exclusões:</span><span class="sxs-lookup"><span data-stu-id="4ebe3-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="4ebe3-320">Diretório de Dispositivos Local em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="4ebe3-321">Diretório de Sites Remotos em cada máquina.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="4ebe3-322">O Diretório de Sites Local no computador hospeda a pasta raiz do site compartilhado.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="4ebe3-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4ebe3-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="4ebe3-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="4ebe3-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="4ebe3-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="4ebe3-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="4ebe3-326">O processo Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="4ebe3-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>