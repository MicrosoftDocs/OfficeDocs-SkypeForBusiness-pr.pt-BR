---
title: Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
ms.openlocfilehash: 9be385030ad09e73608b461c5a0c05cea70987c0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219399"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="b3f7e-103">Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="b3f7e-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="b3f7e-104">Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="b3f7e-105">Portal Administrativo</span><span class="sxs-lookup"><span data-stu-id="b3f7e-105">Administrative Portal</span></span>

<span data-ttu-id="b3f7e-106">Para Skype para implantações em instalações de Business Server, você pode usar o portal do sistema de sala Skype administrativo ativamente gerenciar e monitorar implantações de sistemas de sala Skype dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="b3f7e-107">Consulte o artigo a seguir para obter mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="b3f7e-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="b3f7e-108">Implantar o Portal de Web administrativo do SRS v1 no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b3f7e-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="b3f7e-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="b3f7e-109">System Center Operations Manager</span></span>

<span data-ttu-id="b3f7e-110">Sistema de sala Skype podem ser monitorado por meio do System Center Operations Manager (SCOM) baixando o [Pacote de gerenciamento de sistema do Skype sala](https://www.microsoft.com/download/details.aspx?id=42320) e instalá-lo em seu servidor SCOM.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="b3f7e-111">Você pode usar o SCOM para definir alertas, monitorar a integridade do sistema do Skype sala, gerar relatórios de tempo de atividade e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="b3f7e-112">Sistema de sala do Skype vem com um agente de monitoramento pré-instaladas que pode ser configurado para apontar para o servidor SCOM.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="b3f7e-113">Consulte o guia de instalação fornecido pelo fabricante do seu sistema de sala Skype para saber como configurar o agente de monitoramento no sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="b3f7e-114">Verificação do Exchange</span><span class="sxs-lookup"><span data-stu-id="b3f7e-114">Exchange Checklist</span></span>

- <span data-ttu-id="b3f7e-115">O item Confirmar a Descoberta Automática é configurado e um DNS A/CNAME RECORD está disponível para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="b3f7e-116">Executar o ping de descoberta automática (por exemplo, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="b3f7e-117">Teste seu serviço de Descoberta Automática com a Ferramenta de Análise de Conectividade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="b3f7e-118">Escolha o primeiro teste, "Eu não pode fazer logon com o Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="b3f7e-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="b3f7e-119">Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala Skype (script de exemplo na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="b3f7e-120">Skype para a lista de verificação de negócios</span><span class="sxs-lookup"><span data-stu-id="b3f7e-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="b3f7e-121">Executar as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="b3f7e-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="b3f7e-122">Skype para negócios Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="b3f7e-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="b3f7e-123">Skype para ferramenta de análise de integridade comercial (Excel)</span><span class="sxs-lookup"><span data-stu-id="b3f7e-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="b3f7e-124">Skype para o analisador de conectividade de negócios, 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="b3f7e-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="b3f7e-125">Examine a [solução de problemas novo útil e ferramentas de análise para o Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="b3f7e-126">Confirme que você tem um Skype para pool de negócios e um servidor de Office Web Apps e pode compartilhar um deck de PowerPoint usando o Skype para clientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="b3f7e-127">Se a sala de reunião já tiver uma caixa de correio de recurso, você deve ativá-lo para Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="b3f7e-128">Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="b3f7e-129">Rede</span><span class="sxs-lookup"><span data-stu-id="b3f7e-129">Network</span></span>

- <span data-ttu-id="b3f7e-130">Verifique se que você tem uma conexão de rede com fio para o sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="b3f7e-131">Leia a guia de planejamento para Skype para negócios de rede.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="b3f7e-132">Solicite uma Skype para avaliação da rede de negócios de uma Skype para parceiro de negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="b3f7e-133">Ler os dados de desempenho capturados no Skype para ferramenta de análise de integridade comercial (Excel).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="b3f7e-134">Execute a Ferramenta de Análise de Rede.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="b3f7e-135">Execute a Ferramenta de Pré-diagnóstico de chamada.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="b3f7e-136">Segurança do sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="b3f7e-136">Skype Room System Security</span></span>

<span data-ttu-id="b3f7e-137">Sistema de sala Skype é um sistema de incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o Skype para o modelo de segurança de negócios, gerenciamento de direitos e ferramentas de gerenciamento, como o SCOM.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="b3f7e-138">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="b3f7e-138">Features include:</span></span>
  
- <span data-ttu-id="b3f7e-139">Um Filtro de Gravação para impedir gravações de disco no modo usuário</span><span class="sxs-lookup"><span data-stu-id="b3f7e-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="b3f7e-p105">Bloqueador de aplicativos para impedir que aplicativos não autorizados sejam executados. Todas as portas USB estão desabilitadas no modo usuário.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="b3f7e-142">Nenhum apps standard ou visualizadores residem no hardware do sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="b3f7e-143">Todo o conteúdo é processado por meio de protocolos HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="b3f7e-p107">O PC executa o sistema operacional Padrão 7 Incorporado do Windows. Todo o hardware, incluindo dispositivos, é fornecido pelos parceiros de OEM.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="b3f7e-146">Ingresso Opcional de Domínio para Serviços de Domínio do Active Directory (AD DS), permitindo gerenciamento e controle de contas de segurança local.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="b3f7e-147">Você também pode gerenciar a conta de administrador local usando o Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="b3f7e-148">Sistema de sala Skype for atualizado por meio de processos padrão do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="b3f7e-149">Sistema de sala Skype conecta-se com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="b3f7e-150">Skype para negócios usa criptografia de ponta a ponta e autorização para todos os modos de comunicação</span><span class="sxs-lookup"><span data-stu-id="b3f7e-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="b3f7e-151">Sistema de sala Skype suporta Skype para padrões de segurança e conformidade de negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="b3f7e-152">Para obter mais informações, consulte [Planejar a segurança no Skype para Business Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="b3f7e-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="b3f7e-153">Licença</span><span class="sxs-lookup"><span data-stu-id="b3f7e-153">License</span></span>

<span data-ttu-id="b3f7e-154">Verify that you use a KMS for activating software.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="b3f7e-155">Nesse caso, você talvez precisem verificar ou adicionar o Skype para a chave KMS do cliente de negócios a ela.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="b3f7e-156">Se você não estiver usando o KMS, em seguida, solicite o chave de licenciamento para o Skype para o cliente de negócios MAK por volume.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="b3f7e-157">Chaves de Licença</span><span class="sxs-lookup"><span data-stu-id="b3f7e-157">License keys</span></span>

<span data-ttu-id="b3f7e-158">Skype sala sistema executa o Skype para o cliente de desktop de negócios em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="b3f7e-159">Se o sistema de sala do Skype é um membro do domínio, ele descobre seu KMS.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="b3f7e-160">(e se ele tiver a chave KMS de licenciamento do Volume será ativado automaticamente).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="b3f7e-161">O Licenciamento do Volume também oferece um MAK, que você digita quando ele exibe xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="b3f7e-162">(Você precisa ter acesso à Internet para ativar utilizando o MAK, mas não o KMS).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="b3f7e-163">Para obter mais informações, consulte ativação do Volume do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="b3f7e-164">Para inserir a chave MAK, vá para configurações de OEM \> SRS Licensing Tool.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="b3f7e-165">Clique em Verificar Estado.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-165">Click Check Status.</span></span> <span data-ttu-id="b3f7e-166">Quando o status diz "produto não está ativado", digite a chave.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="b3f7e-167">Se durante a ativação, você receber um erro que diz, "' o serviço de licenciamento de Software relatou que a chave do produto é inválida," Verifique se que:</span><span class="sxs-lookup"><span data-stu-id="b3f7e-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="b3f7e-168">A chave foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="b3f7e-169">Você inseriu o Skype para chave MAK de negócios e não outra chave.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="b3f7e-170">O sistema tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="b3f7e-171">Você pode ativá-lo por telefone, mas deve tentar ativá-lo usando primeiramente a Ferramenta de Licenciamento de SRS.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="b3f7e-172">Para ativá-lo por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta).</span><span class="sxs-lookup"><span data-stu-id="b3f7e-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="b3f7e-173">No Assistente de ativação do Office, selecione a ativação por telefone, ligue para a Microsoft, digite o número longo e digite uma resposta.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="b3f7e-174">Autoridade de Certificação</span><span class="sxs-lookup"><span data-stu-id="b3f7e-174">Certificate Authority</span></span>

<span data-ttu-id="b3f7e-175">Confirme se a Autoridade de Certificação utilizada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade de Listas de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="b3f7e-176">Importe o arquivo de certificado (. crt) para o sistema de sala Skype se estiver usando o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="b3f7e-177">Pode ser facilmente obtido no compartilhamento CertEnroll do servidor CA ou na pasta Raiz Confiável de qualquer PC que participe do domínio.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="b3f7e-178">Certificados</span><span class="sxs-lookup"><span data-stu-id="b3f7e-178">Certificates</span></span>

<span data-ttu-id="b3f7e-p114">Verifique se sua Autoridade de Certificação tem um caminho de http para a lista de Revogação de Certificados. Se não tiver, atualize a sua CA para incluir um.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="b3f7e-181">Instalar certificados na configuração do administrador do sistema Skype sala em configurações do sistema \> Gerenciador de certificados.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="b3f7e-182">Você precisa de um CA de Raiz Corporativa para seu certificado interno.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="b3f7e-183">Uma maneira de obter os certificados que você precisa consiste em descobrir a CA que emitiu seus certificados.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="b3f7e-184">Skype para Business Server, em um PC em Skype para a empresa, clique em configurações \> ferramentas \> configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="b3f7e-185">Isso abre uma página da web protegido pela autoridade de certificação que emitiu os certificados internos.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="b3f7e-186">Clique no ícone de Cadeado na barra de endereço do navegador para exibir um relatório de segurança.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="b3f7e-187">Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição de CRL.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="b3f7e-188">O segundo parâmetro de CN deve ser o nome do servidor de CA.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="b3f7e-189">Abra o Windows Explorer para esse endereço agora \\ \< nome do servidor CA \>\CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="b3f7e-190">Copie o dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="b3f7e-191">Importe o arquivo. CRT para o sistema de sala Skype sob a pasta autoridades de certificação da sala.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="b3f7e-192">Importe os arquivos. CRL no sistema de sala Skype sob a pasta autoridades de certificação intermediários.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="b3f7e-193">(Será necessário alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para visualizar os arquivos.)</span><span class="sxs-lookup"><span data-stu-id="b3f7e-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="b3f7e-194">Observação: O servidor de Office Web Apps 2013 pode compartilhar a mesma CA que Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="b3f7e-195">Caso contrário, você não poderá compartilhar PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="b3f7e-196">Verifique com o departamento de TI e permita que os arquivos CRT e CRL fora da rede de CA compartilhem CertEnroll como explicado acima.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="b3f7e-197">A associação de domínio pode simplificar algumas coisas porque você pode tratar o sistema de sala Skype como um sistema Windows, e ele pode depender do Active Directory para alguns dos aspectos de certificado.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="b3f7e-198">No entanto, é melhor gerenciar este assunto manualmente.</span><span class="sxs-lookup"><span data-stu-id="b3f7e-198">However, it's best to manually manage this.</span></span>
  

