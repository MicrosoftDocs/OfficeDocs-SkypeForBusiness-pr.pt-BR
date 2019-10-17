---
title: Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.
ms.openlocfilehash: c9289d3fffa78dd7ffd94fa17784c1b06c2278b1
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547254"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="17c3d-103">Ferramentas e capacidade de gerenciamento do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="17c3d-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="17c3d-104">Leia este tópico para aprender sobre o gerenciamento de ferramentas para o Sistema de Salas do Skype.</span><span class="sxs-lookup"><span data-stu-id="17c3d-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="17c3d-105">Portal Administrativo</span><span class="sxs-lookup"><span data-stu-id="17c3d-105">Administrative Portal</span></span>

<span data-ttu-id="17c3d-106">Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do sistema de sala do Skype para gerenciar e monitorar ativamente implantações do sistema de sala do Skype dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="17c3d-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="17c3d-107">Para obter mais detalhes, consulte o artigo a seguir:</span><span class="sxs-lookup"><span data-stu-id="17c3d-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="17c3d-108">Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="17c3d-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="17c3d-109">Verificação do Exchange</span><span class="sxs-lookup"><span data-stu-id="17c3d-109">Exchange Checklist</span></span>

- <span data-ttu-id="17c3d-110">O item Confirmar a Descoberta Automática é configurado e um DNS A/CNAME RECORD está disponível para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="17c3d-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="17c3d-111">Executar o ping de descoberta automática (por exemplo, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="17c3d-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="17c3d-112">Teste seu serviço de Descoberta Automática com a Ferramenta de Análise de Conectividade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17c3d-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="17c3d-113">Escolher o primeiro teste, "não é possível fazer logon com o Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="17c3d-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="17c3d-114">Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o sistema de sala da Skype (exemplo de script na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="17c3d-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="17c3d-115">Lista de verificação do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="17c3d-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="17c3d-116">Executar as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="17c3d-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="17c3d-117">Analisador de práticas recomendadas do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="17c3d-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="17c3d-118">Ferramenta de análise de integridade do Skype for Business (Excel)</span><span class="sxs-lookup"><span data-stu-id="17c3d-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="17c3d-119">Analisador de conectividade do Skype for Business 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="17c3d-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="17c3d-120">Revise [novas ferramentas úteis de solução de problemas e análise para o Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="17c3d-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="17c3d-121">Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar uma apresentação do PowerPoint usando o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="17c3d-122">Se a sala de reunião já tiver uma caixa de correio de recurso, habilite-a para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="17c3d-123">Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="17c3d-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="17c3d-124">Rede</span><span class="sxs-lookup"><span data-stu-id="17c3d-124">Network</span></span>

- <span data-ttu-id="17c3d-125">Verifique se você tem uma conexão de rede com fio para o sistema de sala da Skype.</span><span class="sxs-lookup"><span data-stu-id="17c3d-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="17c3d-126">Leia o guia de planejamento de rede para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="17c3d-127">Solicite uma avaliação de rede do Skype for Business a partir de um parceiro do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="17c3d-128">Leia os dados de desempenho capturados na ferramenta de análise de integridade do Skype for Business (Excel).</span><span class="sxs-lookup"><span data-stu-id="17c3d-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="17c3d-129">Execute a Ferramenta de Análise de Rede.</span><span class="sxs-lookup"><span data-stu-id="17c3d-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="17c3d-130">Execute a Ferramenta de Pré-diagnóstico de chamada.</span><span class="sxs-lookup"><span data-stu-id="17c3d-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="17c3d-131">Segurança do sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="17c3d-131">Skype Room System Security</span></span>

<span data-ttu-id="17c3d-132">O sistema de salas da Skype é um sistema integrado que pode ser totalmente integrado a uma implantação do Windows, usando o modelo de segurança do Skype for Business, o gerenciamento de direitos e as ferramentas de gerenciamento, como o SCOM.</span><span class="sxs-lookup"><span data-stu-id="17c3d-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="17c3d-133">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="17c3d-133">Features include:</span></span>
  
- <span data-ttu-id="17c3d-134">Um Filtro de Gravação para impedir gravações de disco no modo usuário</span><span class="sxs-lookup"><span data-stu-id="17c3d-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="17c3d-p104">Bloqueador de aplicativos para impedir que aplicativos não autorizados sejam executados. Todas as portas USB estão desabilitadas no modo usuário.</span><span class="sxs-lookup"><span data-stu-id="17c3d-p104">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="17c3d-137">Nenhum aplicativo ou Visualizador padrão reside no hardware do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="17c3d-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="17c3d-138">Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="17c3d-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="17c3d-p106">O PC executa o sistema operacional Padrão 7 Incorporado do Windows. Todo o hardware, incluindo dispositivos, é fornecido pelos parceiros de OEM.</span><span class="sxs-lookup"><span data-stu-id="17c3d-p106">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="17c3d-141">Ingresso Opcional de Domínio para Serviços de Domínio do Active Directory (AD DS), permitindo gerenciamento e controle de contas de segurança local.</span><span class="sxs-lookup"><span data-stu-id="17c3d-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="17c3d-142">Você também pode gerenciar a conta de administrador local usando o centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="17c3d-143">O sistema de sala do Skype é atualizado por meio de processos padrão do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="17c3d-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="17c3d-144">O sistema da sala Skype se conecta ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="17c3d-145">O Skype for Business usa a autorização e a criptografia ponto a ponto para todos os modos de comunicação</span><span class="sxs-lookup"><span data-stu-id="17c3d-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="17c3d-146">O sistema de sala da Skype é compatível com os padrões de conformidade e segurança do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="17c3d-147">Para obter mais informações, consulte [planejar a segurança no Skype for Business Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="17c3d-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="17c3d-148">Licença</span><span class="sxs-lookup"><span data-stu-id="17c3d-148">License</span></span>

<span data-ttu-id="17c3d-149">Verify that you use a KMS for activating software.</span><span class="sxs-lookup"><span data-stu-id="17c3d-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="17c3d-150">Em caso afirmativo, talvez seja necessário verificar ou adicionar a chave KMS do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="17c3d-151">Se você não estiver usando o KMS, solicite a chave de licenciamento por volume para a MAK do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="17c3d-152">Chaves de Licença</span><span class="sxs-lookup"><span data-stu-id="17c3d-152">License keys</span></span>

<span data-ttu-id="17c3d-153">O sistema de sala do Skype executa o cliente de desktop do Skype for Business em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="17c3d-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="17c3d-154">Se o sistema de sala da Skype for um membro do domínio, ele descobrirá seu KMS.</span><span class="sxs-lookup"><span data-stu-id="17c3d-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="17c3d-155">(e se tiver a chave KMS de licenciamento por volume, ela será ativada automaticamente).</span><span class="sxs-lookup"><span data-stu-id="17c3d-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="17c3d-156">O Licenciamento do Volume também oferece um MAK, que você digita quando ele exibe xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="17c3d-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="17c3d-157">(Você precisa ter acesso à Internet para ativar utilizando o MAK, mas não o KMS).</span><span class="sxs-lookup"><span data-stu-id="17c3d-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="17c3d-158">Para obter mais informações, consulte ativação do Volume do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="17c3d-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="17c3d-159">Para inserir a chave MAK, acesse a ferramenta \> de licenciamento SRS de configurações de OEM.</span><span class="sxs-lookup"><span data-stu-id="17c3d-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="17c3d-160">Clique em Verificar Estado.</span><span class="sxs-lookup"><span data-stu-id="17c3d-160">Click Check Status.</span></span> <span data-ttu-id="17c3d-161">Quando o status diz "produto não está ativado", insira a chave.</span><span class="sxs-lookup"><span data-stu-id="17c3d-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="17c3d-162">Se durante a ativação você receber um erro dizendo que "' o serviço de licenciamento de software informou que a chave do produto é inválida", verifique se:</span><span class="sxs-lookup"><span data-stu-id="17c3d-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="17c3d-163">A chave foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="17c3d-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="17c3d-164">Você inseriu a chave MAK do Skype for Business e não outra chave.</span><span class="sxs-lookup"><span data-stu-id="17c3d-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="17c3d-165">O sistema tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="17c3d-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="17c3d-166">Você pode ativá-lo por telefone, mas deve tentar ativá-lo usando primeiramente a Ferramenta de Licenciamento de SRS.</span><span class="sxs-lookup"><span data-stu-id="17c3d-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="17c3d-167">Para ativá-lo por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta).</span><span class="sxs-lookup"><span data-stu-id="17c3d-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="17c3d-168">No Assistente para ativação do Office, selecione ativação por telefone, ligue para a Microsoft, digite o número longo e digite uma resposta.</span><span class="sxs-lookup"><span data-stu-id="17c3d-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="17c3d-169">Autoridade de Certificação</span><span class="sxs-lookup"><span data-stu-id="17c3d-169">Certificate Authority</span></span>

<span data-ttu-id="17c3d-170">Confirme se a Autoridade de Certificação utilizada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade de Listas de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="17c3d-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="17c3d-171">Importe o arquivo de certificado (. CRT) para o sistema de sala da Skype se estiver usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="17c3d-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="17c3d-172">Pode ser facilmente obtido no compartilhamento CertEnroll do servidor CA ou na pasta Raiz Confiável de qualquer PC que participe do domínio.</span><span class="sxs-lookup"><span data-stu-id="17c3d-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="17c3d-173">Certificados</span><span class="sxs-lookup"><span data-stu-id="17c3d-173">Certificates</span></span>

<span data-ttu-id="17c3d-p113">Verifique se sua Autoridade de Certificação tem um caminho de http para a lista de Revogação de Certificados. Se não tiver, atualize a sua CA para incluir um.</span><span class="sxs-lookup"><span data-stu-id="17c3d-p113">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="17c3d-176">Instale certificados na configuração do administrador do sistema de salas da Skype, em \> Gerenciador de certificados de configurações do sistema.</span><span class="sxs-lookup"><span data-stu-id="17c3d-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="17c3d-177">Você precisa de um CA de Raiz Corporativa para seu certificado interno.</span><span class="sxs-lookup"><span data-stu-id="17c3d-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="17c3d-178">Uma maneira de obter os certificados que você precisa consiste em descobrir a CA que emitiu seus certificados.</span><span class="sxs-lookup"><span data-stu-id="17c3d-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="17c3d-179">Para o Skype for Business Server, em um PC no Skype for Business, clique \> em \> ferramentas de configurações, configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="17c3d-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="17c3d-180">Isso abre uma página da Web protegida pela autoridade de certificação que emitiu os certificados internos.</span><span class="sxs-lookup"><span data-stu-id="17c3d-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="17c3d-181">Clique no ícone de Cadeado na barra de endereço do navegador para exibir um relatório de segurança.</span><span class="sxs-lookup"><span data-stu-id="17c3d-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="17c3d-182">Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição de CRL.</span><span class="sxs-lookup"><span data-stu-id="17c3d-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="17c3d-183">O segundo parâmetro de CN deve ser o nome do servidor de CA.</span><span class="sxs-lookup"><span data-stu-id="17c3d-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="17c3d-184">Agora, abra o Windows Explorer para \\ \< esse nome \>de servidor de CA de endereço \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="17c3d-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="17c3d-185">Copie o dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.</span><span class="sxs-lookup"><span data-stu-id="17c3d-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="17c3d-186">Importe o arquivo. CRT para o sistema de sala do Skype na pasta de autoridade de certificação de sala confiável.</span><span class="sxs-lookup"><span data-stu-id="17c3d-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="17c3d-187">Importe os arquivos. CRL no sistema de sala do Skype na pasta autoridades de certificação intermediárias.</span><span class="sxs-lookup"><span data-stu-id="17c3d-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="17c3d-188">(Será necessário alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para visualizar os arquivos.)</span><span class="sxs-lookup"><span data-stu-id="17c3d-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="17c3d-189">Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA que o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="17c3d-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="17c3d-190">Caso contrário, você não poderá compartilhar PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="17c3d-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="17c3d-191">Verifique com o departamento de TI e permita que os arquivos CRT e CRL fora da rede de CA compartilhem CertEnroll como explicado acima.</span><span class="sxs-lookup"><span data-stu-id="17c3d-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="17c3d-192">A associação de domínio pode simplificar alguns itens porque você pode tratar o sistema de sala da Skype como um sistema do Windows e pode depender do Active Directory para alguns dos aspectos do certificado.</span><span class="sxs-lookup"><span data-stu-id="17c3d-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="17c3d-193">No entanto, é melhor gerenciar este assunto manualmente.</span><span class="sxs-lookup"><span data-stu-id="17c3d-193">However, it's best to manually manage this.</span></span>
  

