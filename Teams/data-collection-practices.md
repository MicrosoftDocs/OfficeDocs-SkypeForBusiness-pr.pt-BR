---
title: Práticas de coleta de dados
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Saiba como a Microsoft coleta dados do censo, do uso e do erro para compreender o Microsoft Teams e os problemas e o uso do Skype for Business para planejar melhorias de produtos.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691527"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="9e91c-103">Práticas de coleta de dados do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e91c-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="9e91c-104">O Skype for Business Server e o Skype for Business Online, juntamente com os aplicativos Skype for Business e Microsoft Teams, coletam dados para ajudar a Microsoft a entender como esses produtos são usados e quais tipos de erros, como erros de conexão, ocorreram.</span><span class="sxs-lookup"><span data-stu-id="9e91c-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="9e91c-105">Essas informações nos ajudam a entender os padrões de uso, planejar novos recursos e solucionar problemas e áreas de problemas.</span><span class="sxs-lookup"><span data-stu-id="9e91c-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="9e91c-106">Enquanto alguns dados de uso são coletados automaticamente, outros dados só podem ser coletados quando o administrador e/ou o usuário optar por permitir isso.</span><span class="sxs-lookup"><span data-stu-id="9e91c-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="9e91c-107">A coleta de dados se encaixa nestas três categorias:</span><span class="sxs-lookup"><span data-stu-id="9e91c-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="9e91c-108">Dados do censo</span><span class="sxs-lookup"><span data-stu-id="9e91c-108">Census data</span></span>

- <span data-ttu-id="9e91c-109">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="9e91c-109">Usage data</span></span>

- <span data-ttu-id="9e91c-110">Dados de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="9e91c-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="9e91c-111">Dados do censo</span><span class="sxs-lookup"><span data-stu-id="9e91c-111">Census data</span></span>

<span data-ttu-id="9e91c-112">Os dados do censo são adquiridos exclusivamente para fornecer, dar suporte e melhorar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9e91c-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="9e91c-113">Microsoft Teams e Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9e91c-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="9e91c-114">Inclui informações ambientais, como versões de dispositivos e sistemas operacionais e configurações regionais e de idioma.</span><span class="sxs-lookup"><span data-stu-id="9e91c-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="9e91c-115">Ele também inclui contadores para tentativas e falhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="9e91c-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="9e91c-116">Aqui estão alguns exemplos específicos dos dados do censo coletados:</span><span class="sxs-lookup"><span data-stu-id="9e91c-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="9e91c-117">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9e91c-117">**Data type**</span></span>|<span data-ttu-id="9e91c-118">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9e91c-118">**Example**</span></span>|<span data-ttu-id="9e91c-119">**Observações**</span><span class="sxs-lookup"><span data-stu-id="9e91c-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e91c-120">AppName</span><span class="sxs-lookup"><span data-stu-id="9e91c-120">AppName</span></span>  <br/> |<span data-ttu-id="9e91c-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="9e91c-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="9e91c-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="9e91c-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="9e91c-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="9e91c-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="9e91c-124">OSName</span><span class="sxs-lookup"><span data-stu-id="9e91c-124">OSName</span></span>  <br/> |<span data-ttu-id="9e91c-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="9e91c-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="9e91c-126">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9e91c-126">OSVersion</span></span>  <br/> |<span data-ttu-id="9e91c-127">8,3</span><span class="sxs-lookup"><span data-stu-id="9e91c-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="9e91c-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="9e91c-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="9e91c-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="9e91c-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="9e91c-130">ID</span><span class="sxs-lookup"><span data-stu-id="9e91c-130">UserID</span></span>  <br/> |<span data-ttu-id="9e91c-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="9e91c-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="9e91c-132">A ID é codificada duas vezes: uma vez no cliente e novamente no serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="9e91c-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="9e91c-133">O hash garante que a identificação não pode ser vinculada a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="9e91c-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="9e91c-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="9e91c-134">DeviceID</span></span>  <br/> |<span data-ttu-id="9e91c-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="9e91c-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="9e91c-136">A ID do dispositivo é um GUID gerado aleatoriamente uma vez no dispositivo e enviado ao serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="9e91c-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="9e91c-137">Os dados do censo não contêm nenhuma informação que identifique sua organização ou seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9e91c-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="9e91c-138">Consulte a [declaração de privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e91c-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="9e91c-139">Os dados do censo são ativados por padrão e não podem ser desativados por administradores ou usuários finais.</span><span class="sxs-lookup"><span data-stu-id="9e91c-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="9e91c-140">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="9e91c-140">Usage data</span></span>

<span data-ttu-id="9e91c-141">Os dados de uso incluem informações como o número de chamadas feitas, o número de mensagens de chat enviadas ou recebidas, o número de reuniões associadas, a frequência de recursos usados e problemas de estabilidade.</span><span class="sxs-lookup"><span data-stu-id="9e91c-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="9e91c-142">Os dados de uso podem conter informações que identificam sua organização, como contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9e91c-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="9e91c-143">Veja alguns exemplos específicos dos dados de uso coletados:</span><span class="sxs-lookup"><span data-stu-id="9e91c-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="9e91c-144">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9e91c-144">**Data type**</span></span>|<span data-ttu-id="9e91c-145">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9e91c-145">**Example**</span></span>|<span data-ttu-id="9e91c-146">**Observações**</span><span class="sxs-lookup"><span data-stu-id="9e91c-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e91c-147">Mensagem instantânea enviada</span><span class="sxs-lookup"><span data-stu-id="9e91c-147">IM Sent</span></span>  <br/> |<span data-ttu-id="9e91c-148">12</span><span class="sxs-lookup"><span data-stu-id="9e91c-148">12</span></span>  <br/> ||
|<span data-ttu-id="9e91c-149">Mensagem instantânea recebida</span><span class="sxs-lookup"><span data-stu-id="9e91c-149">IM Received</span></span>  <br/> |<span data-ttu-id="9e91c-150">5</span><span class="sxs-lookup"><span data-stu-id="9e91c-150">5</span></span>  <br/> ||
|<span data-ttu-id="9e91c-151">Ingressar em uma reunião (tentativas)</span><span class="sxs-lookup"><span data-stu-id="9e91c-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="9e91c-152">5</span><span class="sxs-lookup"><span data-stu-id="9e91c-152">5</span></span>  <br/> ||
|<span data-ttu-id="9e91c-153">Ingressar em uma reunião (sucesso)</span><span class="sxs-lookup"><span data-stu-id="9e91c-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="9e91c-154">4</span><span class="sxs-lookup"><span data-stu-id="9e91c-154">4</span></span>  <br/> ||
|<span data-ttu-id="9e91c-155">Minutos de chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="9e91c-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="9e91c-156">30 minutos</span><span class="sxs-lookup"><span data-stu-id="9e91c-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="9e91c-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="9e91c-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="9e91c-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e91c-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="9e91c-159">Esse é o nome da Organização registrada no Office 365 e é transmitido em texto não criptografado, o que significa que não está ofuscado.</span><span class="sxs-lookup"><span data-stu-id="9e91c-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="9e91c-160">Os dados de uso não contêm informações que identifiquem os usuários.</span><span class="sxs-lookup"><span data-stu-id="9e91c-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="9e91c-161">A coleta de dados de uso está ativada por padrão, mas os administradores locais podem desativá-lo usando a configuração de política de grupo do DisableAutomaticSendTracing no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e91c-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="9e91c-162">Desativar essa configuração afetará todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="9e91c-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="9e91c-163">Consulte [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e91c-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="9e91c-164">Os usuários finais não podem ativar ou desativar a coleta de dados de uso.</span><span class="sxs-lookup"><span data-stu-id="9e91c-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="9e91c-165">Para o aplicativo reuniões do Skype e as páginas da Web do inicializador de junção, a maneira de controlar a telemetria é por meio desta política:</span><span class="sxs-lookup"><span data-stu-id="9e91c-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="9e91c-166">Essa política é definida como false, portanto, a coleta de telemetria está desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9e91c-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="9e91c-167">Essa configuração é por pool e controla todos os usuários que se conectam ao aplicativo reuniões do Skype a uma reunião hospedada nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="9e91c-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="9e91c-168">Dados de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="9e91c-168">Error reporting data</span></span>

<span data-ttu-id="9e91c-169">Os dados de relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração de dispositivo, qualidade da conexão de rede, códigos de erro, logs de erros e exceções.</span><span class="sxs-lookup"><span data-stu-id="9e91c-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="9e91c-170">Veja alguns exemplos específicos de dados de relatório de erros que são coletados:</span><span class="sxs-lookup"><span data-stu-id="9e91c-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="9e91c-171">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9e91c-171">**Data type**</span></span>|<span data-ttu-id="9e91c-172">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9e91c-172">**Example**</span></span>|<span data-ttu-id="9e91c-173">**Observações**</span><span class="sxs-lookup"><span data-stu-id="9e91c-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e91c-174">Direção da mensagem</span><span class="sxs-lookup"><span data-stu-id="9e91c-174">Message direction</span></span>  <br/> |<span data-ttu-id="9e91c-175">Chega</span><span class="sxs-lookup"><span data-stu-id="9e91c-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="9e91c-176">Estado da conversa</span><span class="sxs-lookup"><span data-stu-id="9e91c-176">Conversation state</span></span>  <br/> |<span data-ttu-id="9e91c-177">Ociosidade</span><span class="sxs-lookup"><span data-stu-id="9e91c-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="9e91c-178">ID do thread da conversa</span><span class="sxs-lookup"><span data-stu-id="9e91c-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="9e91c-179">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="9e91c-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="9e91c-180">ID</span><span class="sxs-lookup"><span data-stu-id="9e91c-180">UserID</span></span>  <br/> |<span data-ttu-id="9e91c-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="9e91c-181">amosmarble</span></span> <br/> |<span data-ttu-id="9e91c-182">A ID é enviada em texto sem formatação, que é o hash do serviço de telemetria antes de armazená-lo</span><span class="sxs-lookup"><span data-stu-id="9e91c-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="9e91c-183">Os dados de relatório de erros também podem conter informações de identificação pessoal, como o endereço IP do usuário e o URI de recurso Uniform Resource Identifier (SIP URI).</span><span class="sxs-lookup"><span data-stu-id="9e91c-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="9e91c-184">Consulte a [declaração de privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter uma explicação detalhada do que foi coletado.</span><span class="sxs-lookup"><span data-stu-id="9e91c-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="9e91c-185">O relatório de erros requer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="9e91c-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="9e91c-186">A configuração da política de grupo DisableAutomaticSendTracing é definida como false no servidor ou no centro de administração do locatário (esse é o estado padrão).</span><span class="sxs-lookup"><span data-stu-id="9e91c-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="9e91c-187">Consulte [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e91c-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="9e91c-188">Os usuários finais optam individualmente na guia Geral (clique no ícone de engrenagem ![ um ícone que representa um engrenagem ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e, em seguida, a caixa de diálogo **Opções** é aberta com a guia **geral** exibida) no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9e91c-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Captura de tela da caixa de seleção coleta de dados na caixa de diálogo opções](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="9e91c-190">Para o aplicativo reuniões do Skype, o MeetingUxEnableTelemetry também controla o relatório de erros, embora, no caso de falhas no Windows, controle as configurações do Watson carreguem informações de falha.</span><span class="sxs-lookup"><span data-stu-id="9e91c-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="9e91c-191">Não há nenhuma configuração de usuário para o aplicativo reuniões do Skype como você vê na caixa de diálogo cliente da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9e91c-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="9e91c-192">Consulte [definir opções gerais no Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e91c-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="9e91c-193">Você pode ver [configurar sua rede para o Skype for Business online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="9e91c-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="9e91c-194">Se você estiver usando o Microsoft 365 ou o Office 365 operado pela 21Vianet na China, consulte [configurar sua rede para o Skype for Business online operado pela 21vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="9e91c-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e91c-195">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e91c-195">Related topics</span></span>
[<span data-ttu-id="9e91c-196">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="9e91c-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
