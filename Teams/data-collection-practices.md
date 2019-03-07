---
title: Práticas de coleta de dados
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft coleta dados censo, erro e uso para entender como Skype para negócios está sendo usada e onde os usuários encontrarem problemas. Os dados são usados para planejar os aperfeiçoamentos do produto.
ms.openlocfilehash: d2673424bcddb1b6b3ebaae3bc7bde7f1fce790f
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464112"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="54aa7-104">Skype para práticas de conjunto de dados corporativos e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="54aa7-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="54aa7-105">Skype para Business Server e do Skype para negócios Online, juntamente com o Skype para aplicativos de negócios e Teams da Microsoft, coletar dados para ajudar a compreender como esses produtos estão sendo usados e quais tipos de erros, como erros de entrada, que ocorreram na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54aa7-105">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="54aa7-106">Essas informações nos ajuda a entender os padrões de uso, planejar novos recursos e solucionar problemas e corrigir áreas do problema.</span><span class="sxs-lookup"><span data-stu-id="54aa7-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="54aa7-107">Enquanto alguns dados de uso são coletados automaticamente, outros dados possam ser coletados apenas quando o admin e/ou o usuário optar por permitir que ele.</span><span class="sxs-lookup"><span data-stu-id="54aa7-107">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="54aa7-108">Coleta de dados se enquadra dessas três categorias:</span><span class="sxs-lookup"><span data-stu-id="54aa7-108">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="54aa7-109">Dados Census</span><span class="sxs-lookup"><span data-stu-id="54aa7-109">Census data</span></span>

- <span data-ttu-id="54aa7-110">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="54aa7-110">Usage data</span></span>

- <span data-ttu-id="54aa7-111">Dados de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="54aa7-111">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="54aa7-112">Dados Census</span><span class="sxs-lookup"><span data-stu-id="54aa7-112">Census data</span></span>

<span data-ttu-id="54aa7-113">Dados Census são adquiridos exclusivamente para fornecer, suporte e aprimorar Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="54aa7-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="54aa7-114">As equipes da Microsoft e Skype para negócios on-line.</span><span class="sxs-lookup"><span data-stu-id="54aa7-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="54aa7-115">Ela inclui informações ambientais como versões de dispositivo e o sistema operacional e as configurações regionais e de idioma.</span><span class="sxs-lookup"><span data-stu-id="54aa7-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="54aa7-116">Ele também inclui contadores para tentativas de entrar e falhas.</span><span class="sxs-lookup"><span data-stu-id="54aa7-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="54aa7-117">Aqui estão alguns exemplos específicos dos dados census coletados:</span><span class="sxs-lookup"><span data-stu-id="54aa7-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="54aa7-118">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="54aa7-118">**Data type**</span></span>|<span data-ttu-id="54aa7-119">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="54aa7-119">**Example**</span></span>|<span data-ttu-id="54aa7-120">**Observações**</span><span class="sxs-lookup"><span data-stu-id="54aa7-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54aa7-121">AppName</span><span class="sxs-lookup"><span data-stu-id="54aa7-121">AppName</span></span>  <br/> |<span data-ttu-id="54aa7-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="54aa7-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="54aa7-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="54aa7-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="54aa7-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="54aa7-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="54aa7-125">OSName</span><span class="sxs-lookup"><span data-stu-id="54aa7-125">OSName</span></span>  <br/> |<span data-ttu-id="54aa7-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="54aa7-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="54aa7-127">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="54aa7-127">OSVersion</span></span>  <br/> |<span data-ttu-id="54aa7-128">8.3</span><span class="sxs-lookup"><span data-stu-id="54aa7-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="54aa7-129">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="54aa7-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="54aa7-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="54aa7-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="54aa7-131">UserID</span><span class="sxs-lookup"><span data-stu-id="54aa7-131">UserID</span></span>  <br/> |<span data-ttu-id="54aa7-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="54aa7-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="54aa7-133">A ID é misturada duas vezes: uma vez no cliente e, novamente, o serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="54aa7-133">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="54aa7-134">O hash garante que a ID não pode ser vinculada a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="54aa7-134">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="54aa7-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="54aa7-135">DeviceID</span></span>  <br/> |<span data-ttu-id="54aa7-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="54aa7-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="54aa7-137">ID do dispositivo é um GUID gerado uma vez no dispositivo e enviadas para o serviço de telemetria aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="54aa7-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="54aa7-138">Dados do Census não for contêm alguma informação que identifica a sua organização ou usuários.</span><span class="sxs-lookup"><span data-stu-id="54aa7-138">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="54aa7-139">Consulte o [Skype para a declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54aa7-139">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="54aa7-140">Dados de censo está habilitado por padrão e não podem ser desativados por administradores ou usuários finais.</span><span class="sxs-lookup"><span data-stu-id="54aa7-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="54aa7-141">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="54aa7-141">Usage data</span></span>

<span data-ttu-id="54aa7-142">Dados de uso incluem informações como número de chamadas feitas, número de mensagens instantâneas enviadas ou recebidas, número de reuniões ingressado, frequência dos recursos usados e problemas de estabilidade.</span><span class="sxs-lookup"><span data-stu-id="54aa7-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="54aa7-143">Dados de uso deve conter informações que identifica a sua organização, por exemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="54aa7-143">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="54aa7-144">Aqui estão alguns exemplos específicos dos dados de uso coletados:</span><span class="sxs-lookup"><span data-stu-id="54aa7-144">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="54aa7-145">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="54aa7-145">**Data type**</span></span>|<span data-ttu-id="54aa7-146">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="54aa7-146">**Example**</span></span>|<span data-ttu-id="54aa7-147">**Observações**</span><span class="sxs-lookup"><span data-stu-id="54aa7-147">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54aa7-148">Mensagens Instantâneas enviadas</span><span class="sxs-lookup"><span data-stu-id="54aa7-148">IM Sent</span></span>  <br/> |<span data-ttu-id="54aa7-149">12</span><span class="sxs-lookup"><span data-stu-id="54aa7-149">12</span></span>  <br/> ||
|<span data-ttu-id="54aa7-150">Mensagem Instantânea recebida</span><span class="sxs-lookup"><span data-stu-id="54aa7-150">IM Received</span></span>  <br/> |<span data-ttu-id="54aa7-151">5</span><span class="sxs-lookup"><span data-stu-id="54aa7-151">5</span></span>  <br/> ||
|<span data-ttu-id="54aa7-152">Ingressar em uma reunião (tentativas)</span><span class="sxs-lookup"><span data-stu-id="54aa7-152">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="54aa7-153">5</span><span class="sxs-lookup"><span data-stu-id="54aa7-153">5</span></span>  <br/> ||
|<span data-ttu-id="54aa7-154">Ingressar em uma reunião (sucesso)</span><span class="sxs-lookup"><span data-stu-id="54aa7-154">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="54aa7-155">4</span><span class="sxs-lookup"><span data-stu-id="54aa7-155">4</span></span>  <br/> ||
|<span data-ttu-id="54aa7-156">Minutos de chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="54aa7-156">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="54aa7-157">30 min</span><span class="sxs-lookup"><span data-stu-id="54aa7-157">30 mins</span></span>  <br/> ||
|<span data-ttu-id="54aa7-158">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="54aa7-158">FederationPartner</span></span>  <br/> |<span data-ttu-id="54aa7-159">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="54aa7-159">Microsoft.com</span></span>  <br/> |<span data-ttu-id="54aa7-160">Este é o nome da organização registrada no Office 365 e é transmitido em texto não criptografado, o que significa que ele não é ofuscado.</span><span class="sxs-lookup"><span data-stu-id="54aa7-160">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="54aa7-161">Dados de uso não for contêm alguma informação que identifica os usuários.</span><span class="sxs-lookup"><span data-stu-id="54aa7-161">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="54aa7-162">Coleta de dados de uso está habilitado por padrão, mas os administradores podem desativá-lo usando a configuração de diretiva de grupo DisableAutomaticSendTracing em Skype para Business Server no local.</span><span class="sxs-lookup"><span data-stu-id="54aa7-162">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="54aa7-163">Desativar essa configuração afeta todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="54aa7-163">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="54aa7-164">Consulte [Configure políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54aa7-164">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="54aa7-165">Os usuários finais não podem ativar a coleta de dados de uso ou desativar.</span><span class="sxs-lookup"><span data-stu-id="54aa7-165">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="54aa7-166">Para aplicativos do Skype reuniões e páginas da web de iniciador de ingresso, a maneira de controlar telemetria é por meio dessa diretiva:</span><span class="sxs-lookup"><span data-stu-id="54aa7-166">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="54aa7-167">Essa diretiva padrão é false, portanto a coleção de telemetria está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="54aa7-167">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="54aa7-168">Essa configuração é por pool e controla todos os usuários que se conectam ao Skype reuniões App para uma reunião hospedada nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="54aa7-168">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="54aa7-169">Dados de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="54aa7-169">Error reporting data</span></span>

<span data-ttu-id="54aa7-170">Dados de relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração de dispositivo, qualidade da conexão de rede, códigos de erro, logs de erros e exceções.</span><span class="sxs-lookup"><span data-stu-id="54aa7-170">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="54aa7-171">Aqui estão alguns exemplos específicos de dados coletados de relatório de erros:</span><span class="sxs-lookup"><span data-stu-id="54aa7-171">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="54aa7-172">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="54aa7-172">**Data type**</span></span>|<span data-ttu-id="54aa7-173">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="54aa7-173">**Example**</span></span>|<span data-ttu-id="54aa7-174">**Observações**</span><span class="sxs-lookup"><span data-stu-id="54aa7-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54aa7-175">Direção da mensagem</span><span class="sxs-lookup"><span data-stu-id="54aa7-175">Message direction</span></span>  <br/> |<span data-ttu-id="54aa7-176">Entrada</span><span class="sxs-lookup"><span data-stu-id="54aa7-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="54aa7-177">Estado de conversa</span><span class="sxs-lookup"><span data-stu-id="54aa7-177">Conversation state</span></span>  <br/> |<span data-ttu-id="54aa7-178">Ocioso</span><span class="sxs-lookup"><span data-stu-id="54aa7-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="54aa7-179">ID do thread de conversação</span><span class="sxs-lookup"><span data-stu-id="54aa7-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="54aa7-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="54aa7-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="54aa7-181">UserID</span><span class="sxs-lookup"><span data-stu-id="54aa7-181">UserID</span></span>  <br/> |<span data-ttu-id="54aa7-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="54aa7-182">amosmarble</span></span> <br/> |<span data-ttu-id="54aa7-183">A ID é enviada em texto não criptografado, o serviço de telemetria hashes antes de armazená-lo</span><span class="sxs-lookup"><span data-stu-id="54aa7-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="54aa7-184">Dados de relatórios de erro também podem conter informações de identificação pessoal, como o endereço IP e a sessão Initiation Protocol Uniform Resource Identifier (URI do SIP) do usuário.</span><span class="sxs-lookup"><span data-stu-id="54aa7-184">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="54aa7-185">Consulte o [Skype para a declaração de privacidade de negócios](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para uma explicação detalhada sobre o que é coletado.</span><span class="sxs-lookup"><span data-stu-id="54aa7-185">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="54aa7-186">Relatório de erros exige duas coisas:</span><span class="sxs-lookup"><span data-stu-id="54aa7-186">Error reporting requires two things:</span></span>

- <span data-ttu-id="54aa7-187">A configuração de diretiva de grupo DisableAutomaticSendTracing é definida como False, no servidor ou no Centro de administração de locatário (isto é o estado padrão).</span><span class="sxs-lookup"><span data-stu-id="54aa7-187">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="54aa7-188">Consulte [Configure políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54aa7-188">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="54aa7-189">Os usuários finais individualmente aceitar a partir da guia Geral (clique no ícone de engrenagem ![ícone de engrenagem](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e abre a caixa de diálogo **Opções** com a guia **Geral** exibida) no Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="54aa7-189">End users individually opt in from the General tab (click the gear icon ![Gear icon](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Skype para negócios dados coleção checkbox a caixa de diálogo Opções gt _ gerais](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="54aa7-191">Para o aplicativo do Skype reuniões, o MeetingUxEnableTelemetry também controla relatório de erro, embora para falhas no Windows, as configurações do Watson controlam informações de falha de carregamento.</span><span class="sxs-lookup"><span data-stu-id="54aa7-191">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="54aa7-192">Não há nenhuma configuração do usuário para aplicativo de reuniões do Skype como vê na caixa de diálogo do cliente de desktop.</span><span class="sxs-lookup"><span data-stu-id="54aa7-192">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="54aa7-193">Consulte [Opções gerais definido no Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54aa7-193">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="54aa7-194">Você pode ver a [configurar sua rede para Skype para negócios on-line](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="54aa7-194">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="54aa7-195">Se você estiver usando o Office 365 operado pela 21Vianet na China, consulte [configurar sua rede para Skype para Business Online operado pela 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="54aa7-195">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="54aa7-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="54aa7-196">Related topics</span></span>
[<span data-ttu-id="54aa7-197">Programa de Aperfeiçoamento da experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="54aa7-197">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/default.mspx)

[<span data-ttu-id="54aa7-198">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="54aa7-198">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
