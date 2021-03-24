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
description: Leia este tópico para saber mais sobre ferramentas de gerenciamento para o Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093545"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="12232-103">Ferramentas e capacidade de gerenciamento do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="12232-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="12232-104">Leia este tópico para saber mais sobre ferramentas de gerenciamento para o Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="12232-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="12232-105">Portal Administrativo</span><span class="sxs-lookup"><span data-stu-id="12232-105">Administrative Portal</span></span>

<span data-ttu-id="12232-106">Para implantações locais do Skype for Business Server, você pode usar o portal administrativo do Sistema de Sala do Skype para gerenciar e monitorar ativamente as implantações do Sistema de Sala do Skype em sua organização.</span><span class="sxs-lookup"><span data-stu-id="12232-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="12232-107">Confira o artigo a seguir para obter mais detalhes:</span><span class="sxs-lookup"><span data-stu-id="12232-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="12232-108">Implantar o SRS v1 Administrative Web Portal no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="12232-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="12232-109">Lista de verificação do Exchange</span><span class="sxs-lookup"><span data-stu-id="12232-109">Exchange Checklist</span></span>

- <span data-ttu-id="12232-110">Confirme se a Descoberta Automática está configurada e um REGISTRO DNS A/CNAME interno está disponível para autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="12232-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="12232-111">Descoberta automática de ping (por exemplo, Ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12232-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="12232-112">Teste seu serviço de Descoberta Automática com a Ferramenta analisador de Conectividade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12232-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="12232-113">Escolha o primeiro teste, "Não consigo fazer logoff com o Office Outlook".</span><span class="sxs-lookup"><span data-stu-id="12232-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="12232-114">Se a sala de reunião já tiver uma caixa de correio de recurso, estenda essa conta para o Sistema de Sala do Skype (script de exemplo na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="12232-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="12232-115">Lista de verificação do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="12232-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="12232-116">Execute as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="12232-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="12232-117">Analisador de Práticas Recomendadas do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="12232-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="12232-118">Ferramenta de Análise de Saúde do Skype for Business (Excel)</span><span class="sxs-lookup"><span data-stu-id="12232-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="12232-119">Analisador de Conectividade do Skype for Business de 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="12232-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="12232-120">Revisar [Novas ferramentas de solução de problemas e análise úteis para o Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="12232-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="12232-121">Confirme se você tem um pool do Skype for Business e um servidor do Office Web Apps e pode compartilhar um deck do PowerPoint usando o cliente skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="12232-122">Se a sala de reunião já tiver uma caixa de correio de recurso, habilita-a para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="12232-123">Se necessário, solicite um DID (número de telefone) para o Sistema de Sala de Reunião e atualize o campo Telefone Geral na ferramenta Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12232-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="12232-124">Rede</span><span class="sxs-lookup"><span data-stu-id="12232-124">Network</span></span>

- <span data-ttu-id="12232-125">Certifique-se de ter uma conexão de rede com fio para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="12232-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="12232-126">Leia o Guia de Planejamento de Rede do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="12232-127">Solicite uma avaliação de rede do Skype for Business de um parceiro do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="12232-128">Leia os dados de desempenho capturados na Ferramenta de Análise de Saúde do Skype for Business (Excel).</span><span class="sxs-lookup"><span data-stu-id="12232-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="12232-129">Execute a Ferramenta de Análise de Rede.</span><span class="sxs-lookup"><span data-stu-id="12232-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="12232-130">Execute a Ferramenta de Diagnóstico de Pré-Chamada.</span><span class="sxs-lookup"><span data-stu-id="12232-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="12232-131">Segurança do sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="12232-131">Skype Room System Security</span></span>

<span data-ttu-id="12232-132">O Sistema de Sala do Skype é um sistema incorporado que pode ser totalmente integrado em uma implantação do Windows, usando o modelo de segurança do Skype for Business, gerenciamento de direitos e ferramentas de gerenciamento, como SCOM.</span><span class="sxs-lookup"><span data-stu-id="12232-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="12232-133">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="12232-133">Features include:</span></span>
  
- <span data-ttu-id="12232-134">Um Filtro de Gravação para impedir gravações de disco no modo de usuário</span><span class="sxs-lookup"><span data-stu-id="12232-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="12232-135">App Locker para impedir a execução de aplicativos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="12232-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="12232-136">Todas as portas USB estão desabilitadas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="12232-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="12232-137">Nenhum aplicativo padrão ou visualizadores reside no hardware do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="12232-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="12232-138">Todo o conteúdo é renderizado por meio de protocolos HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="12232-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="12232-139">O computador do dispositivo executa o sistema operacional Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="12232-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="12232-140">Todo o hardware, incluindo dispositivos, é fornecido por parceiros OEM.</span><span class="sxs-lookup"><span data-stu-id="12232-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="12232-141">A junção de domínio opcional aos Serviços de Domínio do Active Directory (AD DS), habilitando o gerenciamento e o controle de contas de segurança locais.</span><span class="sxs-lookup"><span data-stu-id="12232-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="12232-142">Você também pode gerenciar a conta de administrador local usando o Centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="12232-143">O Sistema de Sala do Skype é atualizado por meio de processos padrão do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="12232-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="12232-144">O Sistema de Sala do Skype se conecta ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="12232-145">O Skype for Business usa criptografia de ponta a ponta e autorização para todos os modos de comunicação</span><span class="sxs-lookup"><span data-stu-id="12232-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="12232-146">O Sistema de Sala do Skype dá suporte aos padrões de segurança e conformidade do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="12232-147">Consulte [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="12232-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="12232-148">Licença</span><span class="sxs-lookup"><span data-stu-id="12232-148">License</span></span>

<span data-ttu-id="12232-149">Verifique se você usa um KMS para ativar software.</span><span class="sxs-lookup"><span data-stu-id="12232-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="12232-150">Em caso afirmado, talvez seja necessário verificar ou adicionar a chave KMS do cliente skype for Business a ela.</span><span class="sxs-lookup"><span data-stu-id="12232-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="12232-151">Se você não estiver usando KMS, solicite a chave de licenciamento por volume para o cliente MAK do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="12232-152">Chaves de licença</span><span class="sxs-lookup"><span data-stu-id="12232-152">License keys</span></span>

<span data-ttu-id="12232-153">O Sistema de Sala do Skype executa o cliente da área de trabalho do Skype for Business em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="12232-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="12232-154">Se o Sistema de Sala do Skype for um membro de domínio, ele descobrirá seu KMS.</span><span class="sxs-lookup"><span data-stu-id="12232-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="12232-155">(e se tiver a chave KMS de Licenciamento por Volume será ativada automaticamente).</span><span class="sxs-lookup"><span data-stu-id="12232-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="12232-156">O Licenciamento por Volume também fornece um MAK, que você insinte à medida que exibe xxxxx-xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="12232-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="12232-157">(Você precisa de acesso à Internet para ativar usando MAK, mas não KMS).</span><span class="sxs-lookup"><span data-stu-id="12232-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="12232-158">Para obter mais informações, consulte Ativação de volume do Office 2013.</span><span class="sxs-lookup"><span data-stu-id="12232-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="12232-159">Para inserir a chave MAK, vá para Ferramenta de Licenciamento do SRS configurações do \> OEM.</span><span class="sxs-lookup"><span data-stu-id="12232-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="12232-160">Clique em Verificar Status.</span><span class="sxs-lookup"><span data-stu-id="12232-160">Click Check Status.</span></span> <span data-ttu-id="12232-161">Quando o status diz "o produto não está ativado", digite a tecla.</span><span class="sxs-lookup"><span data-stu-id="12232-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="12232-162">Se durante a ativação você receber um erro que diga "'O Serviço de Licenciamento de Software reportou que a chave do produto é inválida", verifique se:</span><span class="sxs-lookup"><span data-stu-id="12232-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="12232-163">A chave foi inserida corretamente.</span><span class="sxs-lookup"><span data-stu-id="12232-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="12232-164">Você entrou na chave MAK do Skype for Business e não em outra chave.</span><span class="sxs-lookup"><span data-stu-id="12232-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="12232-165">O sistema tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="12232-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="12232-166">Você pode ativar por telefone, mas deve ter tentado ativar usando a Ferramenta de Licenciamento srs primeiro.</span><span class="sxs-lookup"><span data-stu-id="12232-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="12232-167">Para ativar por telefone, inicie uma reunião de teste (não uma chamada de teste, pois é muito curta).</span><span class="sxs-lookup"><span data-stu-id="12232-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="12232-168">No Assistente de Ativação do Office, selecione Ativação telefônica, chame a Microsoft, digite o número longo e insira uma resposta.</span><span class="sxs-lookup"><span data-stu-id="12232-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="12232-169">Autoridade de Certificação</span><span class="sxs-lookup"><span data-stu-id="12232-169">Certificate Authority</span></span>

<span data-ttu-id="12232-170">Confirme se a Autoridade de Certificação usada para emitir o certificado do Office Web Apps Server 2013 tem um caminho HTTP incluído na propriedade Lista de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="12232-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="12232-171">Importe o arquivo Certificate (.crt) para o Sistema de Sala do Skype se estiver usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="12232-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="12232-172">Ele é facilmente obtido do compartilhamento CertEnroll do servidor ca ou na pasta Raiz Confiável de qualquer computador ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="12232-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="12232-173">Certificados</span><span class="sxs-lookup"><span data-stu-id="12232-173">Certificates</span></span>

<span data-ttu-id="12232-174">Verifique se a Autoridade de Certificação tem um caminho http para a Lista de Revogação de Certificados.</span><span class="sxs-lookup"><span data-stu-id="12232-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="12232-175">Caso não seja, atualize sua AC para incluir um.</span><span class="sxs-lookup"><span data-stu-id="12232-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="12232-176">Instale certificados na configuração de administrador do Sistema de Sala do Skype em System Settings \> Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="12232-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="12232-177">Você precisa da AC Raiz da Empresa para seu certificado interno.</span><span class="sxs-lookup"><span data-stu-id="12232-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="12232-178">Uma maneira de obter os certificados necessários é descobrir a AC que emitiu seus certificados.</span><span class="sxs-lookup"><span data-stu-id="12232-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="12232-179">Para o Skype for Business Server, em um computador no Skype for Business, clique em Configurações \> Ferramentas \> de Discagem configurações de conferência.</span><span class="sxs-lookup"><span data-stu-id="12232-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="12232-180">Isso abre uma página da Web protegida pela AC que emitiu os certificados internos.</span><span class="sxs-lookup"><span data-stu-id="12232-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="12232-181">Clique no ícone Bloquear na barra de endereços do navegador para exibir um relatório de segurança.</span><span class="sxs-lookup"><span data-stu-id="12232-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="12232-182">Clique em Exibir Certificados e examine a propriedade Ponto de Distribuição crl.</span><span class="sxs-lookup"><span data-stu-id="12232-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="12232-183">O segundo parâmetro CN deve ser o nome do servidor da AC.</span><span class="sxs-lookup"><span data-stu-id="12232-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="12232-184">Agora abra o Windows Explorer para esse endereço \\ \< CA Server Name \> \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="12232-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="12232-185">Copie os dois arquivos .crl e o arquivo .crt para uma unidade flash e coloque-o no lado esquerdo da placa SMART.</span><span class="sxs-lookup"><span data-stu-id="12232-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="12232-186">Importe o arquivo .crt para o Sistema de Sala do Skype na pasta Autoridade de Certificação de Sala Confiável.</span><span class="sxs-lookup"><span data-stu-id="12232-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="12232-187">Importe os arquivos .crl no Sistema de Sala do Skype na pasta Autoridades intermediárias de certificados.</span><span class="sxs-lookup"><span data-stu-id="12232-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="12232-188">(Você precisa alterar o filtro de extensão de arquivo no Gerenciador de Certificados para .crl para ver os arquivos).</span><span class="sxs-lookup"><span data-stu-id="12232-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="12232-189">Observação: o servidor do Office Web Apps 2013 pode compartilhar a mesma CA do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="12232-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="12232-190">Se não for, você não poderá compartilhar o PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="12232-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="12232-191">Verifique com a IT e obtenha os arquivos CRT e CRL do compartilhamento de rede da CA CertEnroll conforme explicado acima.</span><span class="sxs-lookup"><span data-stu-id="12232-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="12232-192">A associação de domínio pode simplificar algumas coisas porque você pode tratar o Sistema de Sala do Skype como um sistema Windows e pode contar com o Active Directory para alguns dos aspectos do certificado.</span><span class="sxs-lookup"><span data-stu-id="12232-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="12232-193">No entanto, é melhor gerenciar isso manualmente.</span><span class="sxs-lookup"><span data-stu-id="12232-193">However, it's best to manually manage this.</span></span>
