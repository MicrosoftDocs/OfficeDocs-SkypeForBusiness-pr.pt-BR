---
title: Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leia este tópico para saber mais sobre as ferramentas de gerenciamento para o Sistema de Sala do Skype.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805791"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="49a1d-103">Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="49a1d-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="49a1d-104">Leia este tópico para saber mais sobre as ferramentas de gerenciamento para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="49a1d-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="49a1d-105">Portal Administrativo</span><span class="sxs-lookup"><span data-stu-id="49a1d-105">Administrative Portal</span></span>

<span data-ttu-id="49a1d-106">Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do Sistema de Sala do Skype para gerenciar e monitorar ativamente as implantações do Sistema de Sala do Skype em sua organização.</span><span class="sxs-lookup"><span data-stu-id="49a1d-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="49a1d-107">Consulte o artigo a seguir para obter mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="49a1d-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="49a1d-108">Implantar o Portal da Web Administrativo do SRS v1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49a1d-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="49a1d-109">Lista de verificação do Exchange</span><span class="sxs-lookup"><span data-stu-id="49a1d-109">Exchange Checklist</span></span>

- <span data-ttu-id="49a1d-110">Confirme se a Descoberta Automática está configurada e um REGISTRO DNS A/CNAME interno está disponível para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="49a1d-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="49a1d-111">Ping autodiscover (por exemplo, ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="49a1d-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="49a1d-112">Teste seu serviço de Descoberta Automática com a Ferramenta Analisador de Conectividade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49a1d-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="49a1d-113">Escolha o primeiro teste, "Não consigo fazer logoff com o Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="49a1d-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="49a1d-114">Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o Sistema de Sala do Skype (script de exemplo na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="49a1d-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="49a1d-115">Lista de verificação do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="49a1d-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="49a1d-116">Execute as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="49a1d-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="49a1d-117">Analisador de Práticas Recomendadas do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="49a1d-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="49a1d-118">Ferramenta de Análise de Saúde do Skype for Business (Excel)</span><span class="sxs-lookup"><span data-stu-id="49a1d-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="49a1d-119">Analisador de Conectividade do Skype for Business de 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="49a1d-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="49a1d-120">Revise [as novas ferramentas úteis de solução de problemas e análise do Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)</span><span class="sxs-lookup"><span data-stu-id="49a1d-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="49a1d-121">Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar um conjunto do PowerPoint usando o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="49a1d-122">Se a sala de reunião já tiver uma caixa de correio de recursos, habilita-a para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="49a1d-123">Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49a1d-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="49a1d-124">Rede</span><span class="sxs-lookup"><span data-stu-id="49a1d-124">Network</span></span>

- <span data-ttu-id="49a1d-125">Certifique-se de que você tenha uma conexão de rede com fio para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="49a1d-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="49a1d-126">Leia o Guia de Planejamento de Rede do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="49a1d-127">Solicite uma avaliação de rede do Skype for Business de um parceiro do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="49a1d-128">Leia os dados de desempenho capturados na Ferramenta de Análise de Saúde do Skype for Business (Excel).</span><span class="sxs-lookup"><span data-stu-id="49a1d-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="49a1d-129">Execute a Ferramenta de Análise de Rede.</span><span class="sxs-lookup"><span data-stu-id="49a1d-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="49a1d-130">Execute a Ferramenta de Diagnóstico de Pré-Chamada.</span><span class="sxs-lookup"><span data-stu-id="49a1d-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="49a1d-131">Segurança do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="49a1d-131">Skype Room System Security</span></span>

<span data-ttu-id="49a1d-132">O Sistema de Sala do Skype é um sistema incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o modelo de segurança, gerenciamento de direitos e ferramentas de gerenciamento do Skype for Business, como o SCOM.</span><span class="sxs-lookup"><span data-stu-id="49a1d-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="49a1d-133">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="49a1d-133">Features include:</span></span>
  
- <span data-ttu-id="49a1d-134">Um Filtro de Gravação para impedir gravações de disco no modo de usuário</span><span class="sxs-lookup"><span data-stu-id="49a1d-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="49a1d-135">App Locker para impedir a execução de aplicativos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="49a1d-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="49a1d-136">Todas as portas USB estão desabilitadas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="49a1d-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="49a1d-137">Nenhum aplicativo padrão ou visualizadores residem no hardware do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="49a1d-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="49a1d-138">Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="49a1d-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="49a1d-139">O pc executa o sistema operacional Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="49a1d-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="49a1d-140">Todo o hardware, incluindo dispositivos, é fornecido por parceiros OEM.</span><span class="sxs-lookup"><span data-stu-id="49a1d-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="49a1d-141">O AD DS (Active Directory Domain Services) opcional permite o gerenciamento e o controle da conta de segurança local.</span><span class="sxs-lookup"><span data-stu-id="49a1d-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="49a1d-142">Você também pode gerenciar a conta de administrador local usando o Centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="49a1d-143">O Sistema de Sala do Skype é atualizado por meio de processos padrão do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="49a1d-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="49a1d-144">O Sistema de Sala do Skype se conecta ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="49a1d-145">O Skype for Business usa criptografia e autorização de ponta a ponta para todos os modos de comunicação</span><span class="sxs-lookup"><span data-stu-id="49a1d-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="49a1d-146">O Sistema de Sala do Skype dá suporte aos padrões de segurança e conformidade do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="49a1d-147">Consulte [Plano de segurança no Skype for Business Server](../../plan-your-deployment/security/security.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="49a1d-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="49a1d-148">Licença</span><span class="sxs-lookup"><span data-stu-id="49a1d-148">License</span></span>

<span data-ttu-id="49a1d-149">Verifique se você usa um KMS para ativar o software.</span><span class="sxs-lookup"><span data-stu-id="49a1d-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="49a1d-150">Se for o caso, talvez seja necessário verificar ou adicionar a chave KMS do cliente Skype for Business a ela.</span><span class="sxs-lookup"><span data-stu-id="49a1d-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="49a1d-151">Se você não estiver usando o KMS, solicite a chave de licenciamento por volume para a MAK do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="49a1d-152">Chaves de licença</span><span class="sxs-lookup"><span data-stu-id="49a1d-152">License keys</span></span>

<span data-ttu-id="49a1d-153">O Sistema de Sala do Skype executa o cliente de área de trabalho do Skype for Business em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="49a1d-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="49a1d-154">Se o Sistema de Sala do Skype for um membro do domínio, ele descobrirá seu KMS.</span><span class="sxs-lookup"><span data-stu-id="49a1d-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="49a1d-155">(e se tiver a Chave KMS de Licenciamento por Volume, ela será ativada automaticamente).</span><span class="sxs-lookup"><span data-stu-id="49a1d-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="49a1d-156">O Licenciamento por Volume também fornece uma MAK, que você ins dá ao exibir xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="49a1d-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="49a1d-157">(Você precisa de acesso à Internet para ativar usando MAK, mas não KMS).</span><span class="sxs-lookup"><span data-stu-id="49a1d-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="49a1d-158">Para obter mais informações, consulte a ativação de volume do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="49a1d-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="49a1d-159">Para inserir a chave MAK, vá para a Ferramenta de Licenciamento \> de SRS de Configurações OEM.</span><span class="sxs-lookup"><span data-stu-id="49a1d-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="49a1d-160">Clique em Verificar Status.</span><span class="sxs-lookup"><span data-stu-id="49a1d-160">Click Check Status.</span></span> <span data-ttu-id="49a1d-161">Quando o status diz "o produto não está ativado", insira a chave.</span><span class="sxs-lookup"><span data-stu-id="49a1d-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="49a1d-162">Se durante a ativação você receber um erro que diz" "O Serviço de Licenciamento de Software relatou que a chave do produto é inválida", verifique se:</span><span class="sxs-lookup"><span data-stu-id="49a1d-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="49a1d-163">A chave foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="49a1d-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="49a1d-164">Você entrou na chave MAK do Skype for Business e não em outra chave.</span><span class="sxs-lookup"><span data-stu-id="49a1d-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="49a1d-165">O sistema tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="49a1d-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="49a1d-166">Você pode ativar por telefone, mas deve ter tentado ativar usando primeiro a Ferramenta de Licenciamento do SRS.</span><span class="sxs-lookup"><span data-stu-id="49a1d-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="49a1d-167">Para ativar por telefone, inicie uma reunião de teste (não uma chamada de teste, pois ela é muito curta).</span><span class="sxs-lookup"><span data-stu-id="49a1d-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="49a1d-168">No Assistente de Ativação do Office, selecione Ativação de Telefone, ligue para a Microsoft, digite o número longo e insira uma resposta.</span><span class="sxs-lookup"><span data-stu-id="49a1d-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="49a1d-169">Autoridade de Certificação</span><span class="sxs-lookup"><span data-stu-id="49a1d-169">Certificate Authority</span></span>

<span data-ttu-id="49a1d-170">Confirme se a Autoridade de Certificação usada para emitir o certificado do Office Web Apps Server 2013 possui um caminho HTTP incluído na propriedade da Lista de Certificados Revogados.</span><span class="sxs-lookup"><span data-stu-id="49a1d-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="49a1d-171">Importe o arquivo de certificado (.crt) para o Sistema de Sala do Skype se estiver usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49a1d-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="49a1d-172">Ele é obtido facilmente do compartilhamento CertEnroll do servidor de CA ou na pasta Raiz Confiável de qualquer computador ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="49a1d-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="49a1d-173">Certificados</span><span class="sxs-lookup"><span data-stu-id="49a1d-173">Certificates</span></span>

<span data-ttu-id="49a1d-174">Verifique se a Autoridade de Certificação tem um caminho http para a Lista de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="49a1d-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="49a1d-175">Caso não o seja, atualize sua AC para incluir uma.</span><span class="sxs-lookup"><span data-stu-id="49a1d-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="49a1d-176">Instale certificados na configuração administrativa do Sistema de Sala do Skype no Gerenciador de Certificados de Configurações \> do Sistema.</span><span class="sxs-lookup"><span data-stu-id="49a1d-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="49a1d-177">Você precisa da AC raiz corporativa para seu certificado interno.</span><span class="sxs-lookup"><span data-stu-id="49a1d-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="49a1d-178">Uma maneira de obter os certificados necessários é descobrir a CA que emitiu seus certificados.</span><span class="sxs-lookup"><span data-stu-id="49a1d-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="49a1d-179">Para o Skype for Business Server, em um computador no Skype for Business, clique em Configurações das Ferramentas de \> \> Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="49a1d-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="49a1d-180">Isso abre uma página da Web protegida pela AC que emitiu os certificados internos.</span><span class="sxs-lookup"><span data-stu-id="49a1d-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="49a1d-181">Clique no ícone Bloquear na barra de endereços do navegador para exibir um relatório de segurança.</span><span class="sxs-lookup"><span data-stu-id="49a1d-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="49a1d-182">Clique em Exibir Certificados e examine a propriedade do Ponto de Distribuição da CRL.</span><span class="sxs-lookup"><span data-stu-id="49a1d-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="49a1d-183">O segundo parâmetro CN deve ser o nome do servidor da AC.</span><span class="sxs-lookup"><span data-stu-id="49a1d-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="49a1d-184">Agora abra o Windows Explorer para esse endereço \\ \< CA Server Name \> \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="49a1d-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="49a1d-185">Copie os dois arquivos .crl e o arquivo .crt em uma unidade flash e coloque-os no lado esquerdo da placa SMART.</span><span class="sxs-lookup"><span data-stu-id="49a1d-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="49a1d-186">Importe o arquivo .crt para o Sistema de Sala do Skype na pasta Autoridade de Certificação de Sala Confiável.</span><span class="sxs-lookup"><span data-stu-id="49a1d-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="49a1d-187">Importe os arquivos .crl no Sistema de Sala do Skype na pasta Autoridades de Certificação Intermediárias.</span><span class="sxs-lookup"><span data-stu-id="49a1d-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="49a1d-188">(Você precisa alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para ver os arquivos).</span><span class="sxs-lookup"><span data-stu-id="49a1d-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="49a1d-189">Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA que o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="49a1d-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="49a1d-190">Se isso não for feito, você não poderá compartilhar o PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="49a1d-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="49a1d-191">Verifique com a EQUIPE de IT e obtenha os arquivos CRT e CRL fora do compartilhamento de rede ca CertEnroll conforme explicado acima.</span><span class="sxs-lookup"><span data-stu-id="49a1d-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="49a1d-192">A associação de domínio pode simplificar algumas coisas porque você pode tratar o Sistema de Sala do Skype como um sistema windows e ele pode depender do Active Directory para alguns dos aspectos do certificado.</span><span class="sxs-lookup"><span data-stu-id="49a1d-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="49a1d-193">No entanto, é melhor gerenciar manualmente isso.</span><span class="sxs-lookup"><span data-stu-id="49a1d-193">However, it's best to manually manage this.</span></span>
  

