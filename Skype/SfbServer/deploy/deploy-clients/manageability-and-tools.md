---
title: Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
ms.openlocfilehash: ce33307babac88f6a0e3145988d0ea8519f86110
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234214"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="4b606-103">Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="4b606-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="4b606-104">Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="4b606-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="4b606-105">Portal Administrativo</span><span class="sxs-lookup"><span data-stu-id="4b606-105">Administrative Portal</span></span>

<span data-ttu-id="4b606-106">Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do sistema de sala do Skype para gerenciar e monitorar ativamente implantações do sistema de sala do Skype dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4b606-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="4b606-107">Para obter mais detalhes, consulte o artigo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4b606-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="4b606-108">Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b606-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="4b606-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4b606-109">System Center Operations Manager</span></span>

<span data-ttu-id="4b606-110">O sistema de sala do Skype pode ser monitorado por meio do SCOM (System Center Operations Manager) baixando o [pacote de gerenciamento do sistema de sala do Skype](https://www.microsoft.com/download/details.aspx?id=42320) e instalando-o em seu servidor do SCOM.</span><span class="sxs-lookup"><span data-stu-id="4b606-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="4b606-111">Você pode usar o SCOM para definir alertas, monitorar a integridade do sistema de salas da Skype, gerar relatórios de tempo de atividade e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4b606-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="4b606-112">O sistema de salas da Skype vem com um agente de monitoramento pré-instalado que pode ser configurado para apontar para o servidor do SCOM.</span><span class="sxs-lookup"><span data-stu-id="4b606-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="4b606-113">Consulte o guia de instalação fornecido pelo fabricante do seu sistema de sala do Skype para saber como configurar o agente de monitoramento no sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="4b606-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="4b606-114">Verificação do Exchange</span><span class="sxs-lookup"><span data-stu-id="4b606-114">Exchange Checklist</span></span>

- <span data-ttu-id="4b606-115">O item Confirmar a Descoberta Automática é configurado e um DNS A/CNAME RECORD está disponível para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="4b606-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="4b606-116">Executar o ping de descoberta automática (por exemplo, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4b606-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="4b606-117">Teste seu serviço de Descoberta Automática com a Ferramenta de Análise de Conectividade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b606-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="4b606-118">Escolher o primeiro teste, "não é possível fazer logon com o Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="4b606-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="4b606-119">Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala da Skype (exemplo de script na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="4b606-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="4b606-120">Lista de verificação do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4b606-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="4b606-121">Executar as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="4b606-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="4b606-122">Analisador de práticas recomendadas do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4b606-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="4b606-123">Ferramenta de análise de integridade do Skype for Business (Excel)</span><span class="sxs-lookup"><span data-stu-id="4b606-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="4b606-124">Analisador de conectividade do Skype for Business 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="4b606-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="4b606-125">Revise [novas ferramentas úteis de solução de problemas e análise para o Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="4b606-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="4b606-126">Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar uma apresentação do PowerPoint usando o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="4b606-127">Se a sala de reunião já tiver uma caixa de correio de recurso, habilite-a para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="4b606-128">Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b606-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="4b606-129">Rede</span><span class="sxs-lookup"><span data-stu-id="4b606-129">Network</span></span>

- <span data-ttu-id="4b606-130">Verifique se você tem uma conexão de rede com fio para o sistema de sala da Skype.</span><span class="sxs-lookup"><span data-stu-id="4b606-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="4b606-131">Leia o guia de planejamento de rede para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="4b606-132">Solicite uma avaliação de rede do Skype for Business a partir de um parceiro do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="4b606-133">Leia os dados de desempenho capturados na ferramenta de análise de integridade do Skype for Business (Excel).</span><span class="sxs-lookup"><span data-stu-id="4b606-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="4b606-134">Execute a Ferramenta de Análise de Rede.</span><span class="sxs-lookup"><span data-stu-id="4b606-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="4b606-135">Execute a Ferramenta de Pré-diagnóstico de chamada.</span><span class="sxs-lookup"><span data-stu-id="4b606-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="4b606-136">Segurança do sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="4b606-136">Skype Room System Security</span></span>

<span data-ttu-id="4b606-137">O sistema de salas da Skype é um sistema integrado que pode ser totalmente integrado a uma implantação do Windows, usando o modelo de segurança do Skype for Business, o gerenciamento de direitos e as ferramentas de gerenciamento, como o SCOM.</span><span class="sxs-lookup"><span data-stu-id="4b606-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="4b606-138">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="4b606-138">Features include:</span></span>
  
- <span data-ttu-id="4b606-139">Um Filtro de Gravação para impedir gravações de disco no modo usuário</span><span class="sxs-lookup"><span data-stu-id="4b606-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="4b606-p105">Bloqueador de aplicativos para impedir que aplicativos não autorizados sejam executados. Todas as portas USB estão desabilitadas no modo usuário.</span><span class="sxs-lookup"><span data-stu-id="4b606-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="4b606-142">Nenhum aplicativo ou Visualizador padrão reside no hardware do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="4b606-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="4b606-143">Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="4b606-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="4b606-p107">O PC executa o sistema operacional Padrão 7 Incorporado do Windows. Todo o hardware, incluindo dispositivos, é fornecido pelos parceiros de OEM.</span><span class="sxs-lookup"><span data-stu-id="4b606-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="4b606-146">Ingresso Opcional de Domínio para Serviços de Domínio do Active Directory (AD DS), permitindo gerenciamento e controle de contas de segurança local.</span><span class="sxs-lookup"><span data-stu-id="4b606-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="4b606-147">Você também pode gerenciar a conta de administrador local usando o centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="4b606-148">O sistema de sala do Skype é atualizado por meio de processos padrão do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4b606-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="4b606-149">O sistema da sala Skype se conecta ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="4b606-150">O Skype for Business usa a autorização e a criptografia ponto a ponto para todos os modos de comunicação</span><span class="sxs-lookup"><span data-stu-id="4b606-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="4b606-151">O sistema de sala da Skype é compatível com os padrões de conformidade e segurança do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="4b606-152">Para obter mais informações, consulte [planejar a segurança no Skype for Business Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="4b606-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="4b606-153">Licença</span><span class="sxs-lookup"><span data-stu-id="4b606-153">License</span></span>

<span data-ttu-id="4b606-154">Verify that you use a KMS for activating software.</span><span class="sxs-lookup"><span data-stu-id="4b606-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="4b606-155">Em caso afirmativo, talvez seja necessário verificar ou adicionar a chave KMS do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="4b606-156">Se você não estiver usando o KMS, solicite a chave de licenciamento por volume para a MAK do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="4b606-157">Chaves de Licença</span><span class="sxs-lookup"><span data-stu-id="4b606-157">License keys</span></span>

<span data-ttu-id="4b606-158">O sistema de sala do Skype executa o cliente de desktop do Skype for Business em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4b606-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="4b606-159">Se o sistema de sala da Skype for um membro do domínio, ele descobrirá seu KMS.</span><span class="sxs-lookup"><span data-stu-id="4b606-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="4b606-160">(e se tiver a chave KMS de licenciamento por volume, ela será ativada automaticamente).</span><span class="sxs-lookup"><span data-stu-id="4b606-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="4b606-161">O Licenciamento do Volume também oferece um MAK, que você digita quando ele exibe xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="4b606-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="4b606-162">(Você precisa ter acesso à Internet para ativar utilizando o MAK, mas não o KMS).</span><span class="sxs-lookup"><span data-stu-id="4b606-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="4b606-163">Para obter mais informações, consulte ativação do Volume do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="4b606-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="4b606-164">Para inserir a chave MAK, acesse a ferramenta \> de licenciamento SRS de configurações de OEM.</span><span class="sxs-lookup"><span data-stu-id="4b606-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="4b606-165">Clique em Verificar Estado.</span><span class="sxs-lookup"><span data-stu-id="4b606-165">Click Check Status.</span></span> <span data-ttu-id="4b606-166">Quando o status diz "produto não está ativado", insira a chave.</span><span class="sxs-lookup"><span data-stu-id="4b606-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="4b606-167">Se durante a ativação você receber um erro dizendo que "' o serviço de licenciamento de software informou que a chave do produto é inválida", verifique se:</span><span class="sxs-lookup"><span data-stu-id="4b606-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="4b606-168">A chave foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="4b606-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="4b606-169">Você inseriu a chave MAK do Skype for Business e não outra chave.</span><span class="sxs-lookup"><span data-stu-id="4b606-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="4b606-170">O sistema tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="4b606-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="4b606-171">Você pode ativá-lo por telefone, mas deve tentar ativá-lo usando primeiramente a Ferramenta de Licenciamento de SRS.</span><span class="sxs-lookup"><span data-stu-id="4b606-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="4b606-172">Para ativá-lo por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta).</span><span class="sxs-lookup"><span data-stu-id="4b606-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="4b606-173">No Assistente para ativação do Office, selecione ativação por telefone, ligue para a Microsoft, digite o número longo e digite uma resposta.</span><span class="sxs-lookup"><span data-stu-id="4b606-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="4b606-174">Autoridade de Certificação</span><span class="sxs-lookup"><span data-stu-id="4b606-174">Certificate Authority</span></span>

<span data-ttu-id="4b606-175">Confirme se a Autoridade de Certificação utilizada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade de Listas de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="4b606-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="4b606-176">Importe o arquivo de certificado (. CRT) para o sistema de sala da Skype se estiver usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b606-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="4b606-177">Pode ser facilmente obtido no compartilhamento CertEnroll do servidor CA ou na pasta Raiz Confiável de qualquer PC que participe do domínio.</span><span class="sxs-lookup"><span data-stu-id="4b606-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="4b606-178">Certificados</span><span class="sxs-lookup"><span data-stu-id="4b606-178">Certificates</span></span>

<span data-ttu-id="4b606-p114">Verifique se sua Autoridade de Certificação tem um caminho de http para a lista de Revogação de Certificados. Se não tiver, atualize a sua CA para incluir um.</span><span class="sxs-lookup"><span data-stu-id="4b606-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="4b606-181">Instale certificados na configuração do administrador do sistema de salas da Skype, em \> Gerenciador de certificados de configurações do sistema.</span><span class="sxs-lookup"><span data-stu-id="4b606-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="4b606-182">Você precisa de um CA de Raiz Corporativa para seu certificado interno.</span><span class="sxs-lookup"><span data-stu-id="4b606-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="4b606-183">Uma maneira de obter os certificados que você precisa consiste em descobrir a CA que emitiu seus certificados.</span><span class="sxs-lookup"><span data-stu-id="4b606-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="4b606-184">Para o Skype for Business Server, em um PC no Skype for Business, clique \> em \> ferramentas de configurações, configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="4b606-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="4b606-185">Isso abre uma página da Web protegida pela autoridade de certificação que emitiu os certificados internos.</span><span class="sxs-lookup"><span data-stu-id="4b606-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="4b606-186">Clique no ícone de Cadeado na barra de endereço do navegador para exibir um relatório de segurança.</span><span class="sxs-lookup"><span data-stu-id="4b606-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="4b606-187">Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição de CRL.</span><span class="sxs-lookup"><span data-stu-id="4b606-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="4b606-188">O segundo parâmetro de CN deve ser o nome do servidor de CA.</span><span class="sxs-lookup"><span data-stu-id="4b606-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="4b606-189">Agora, abra o Windows Explorer para \\ \< esse nome \>de servidor de CA de endereço \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="4b606-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="4b606-190">Copie o dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.</span><span class="sxs-lookup"><span data-stu-id="4b606-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="4b606-191">Importe o arquivo. CRT para o sistema de sala do Skype na pasta de autoridade de certificação de sala confiável.</span><span class="sxs-lookup"><span data-stu-id="4b606-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="4b606-192">Importe os arquivos. CRL no sistema de sala do Skype na pasta autoridades de certificação intermediárias.</span><span class="sxs-lookup"><span data-stu-id="4b606-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="4b606-193">(Será necessário alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para visualizar os arquivos.)</span><span class="sxs-lookup"><span data-stu-id="4b606-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="4b606-194">Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA que o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4b606-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="4b606-195">Caso contrário, você não poderá compartilhar PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="4b606-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="4b606-196">Verifique com o departamento de TI e permita que os arquivos CRT e CRL fora da rede de CA compartilhem CertEnroll como explicado acima.</span><span class="sxs-lookup"><span data-stu-id="4b606-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="4b606-197">A associação de domínio pode simplificar alguns itens porque você pode tratar o sistema de sala da Skype como um sistema do Windows e pode depender do Active Directory para alguns dos aspectos do certificado.</span><span class="sxs-lookup"><span data-stu-id="4b606-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="4b606-198">No entanto, é melhor gerenciar este assunto manualmente.</span><span class="sxs-lookup"><span data-stu-id="4b606-198">However, it's best to manually manage this.</span></span>
  

