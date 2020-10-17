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
description: Saiba como a Microsoft coleta dados do censo, do uso e de erros para entender o uso e os problemas do Teams e do Skype for Business para planejar melhorias no produto.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651220"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="9451b-103">Práticas de coleta de dados do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9451b-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="9451b-104">O Skype for Business Server e o Skype for Business Online, junto com os aplicativos do Skype for Business e do Microsoft Teams, coletam dados para ajudar a Microsoft a entender como esses produtos estão sendo usados e quais tipos de erros, como erros de entrada, ocorreram.</span><span class="sxs-lookup"><span data-stu-id="9451b-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="9451b-105">Essas informações nos ajudam a entender os padrões de uso, planejar novos recursos e solucionar problemas e corrigir áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="9451b-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="9451b-106">Enquanto alguns dados de uso são coletados automaticamente, outros dados só podem ser coletados com a permissão do administrador e/ou usuário.</span><span class="sxs-lookup"><span data-stu-id="9451b-106">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it.</span></span> <span data-ttu-id="9451b-107">A coleta de dados se enquadra nestas três categorias:</span><span class="sxs-lookup"><span data-stu-id="9451b-107">Data collection falls into these three categories:</span></span>

- <span data-ttu-id="9451b-108">Dados do censo</span><span class="sxs-lookup"><span data-stu-id="9451b-108">Census data</span></span>

- <span data-ttu-id="9451b-109">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="9451b-109">Usage data</span></span>

- <span data-ttu-id="9451b-110">Dados do relatório de erros</span><span class="sxs-lookup"><span data-stu-id="9451b-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="9451b-111">Dados do censo</span><span class="sxs-lookup"><span data-stu-id="9451b-111">Census data</span></span>

<span data-ttu-id="9451b-112">Os dados do censo são adquiridos exclusivamente para fornecer, dar suporte e melhorar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9451b-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="9451b-113">Microsoft Teams e o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9451b-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="9451b-114">Inclui informações ambientais, como versões do dispositivo e do sistema operacional, além das configurações regionais e de idioma.</span><span class="sxs-lookup"><span data-stu-id="9451b-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="9451b-115">Inclui também contadores para tentativas e falhas de entrada.</span><span class="sxs-lookup"><span data-stu-id="9451b-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="9451b-116">Aqui estão alguns exemplos específicos dos dados coletados do censo:</span><span class="sxs-lookup"><span data-stu-id="9451b-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="9451b-117">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9451b-117">**Data type**</span></span>|<span data-ttu-id="9451b-118">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9451b-118">**Example**</span></span>|<span data-ttu-id="9451b-119">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="9451b-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9451b-120">AppName</span><span class="sxs-lookup"><span data-stu-id="9451b-120">AppName</span></span>  <br/> |<span data-ttu-id="9451b-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="9451b-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="9451b-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="9451b-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="9451b-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="9451b-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="9451b-124">OSName</span><span class="sxs-lookup"><span data-stu-id="9451b-124">OSName</span></span>  <br/> |<span data-ttu-id="9451b-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="9451b-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="9451b-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="9451b-126">OSVersion</span></span>  <br/> |<span data-ttu-id="9451b-127">8.3</span><span class="sxs-lookup"><span data-stu-id="9451b-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="9451b-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="9451b-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="9451b-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="9451b-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="9451b-130">UserID</span><span class="sxs-lookup"><span data-stu-id="9451b-130">UserID</span></span>  <br/> |<span data-ttu-id="9451b-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="9451b-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="9451b-132">A ID é transformada em hash duas vezes: uma vez no cliente e novamente no serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="9451b-132">The ID is hashed twice: once on the client and again on the telemetry service.</span></span> <span data-ttu-id="9451b-133">O hash garante que a ID não possa ser vinculada a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="9451b-133">The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="9451b-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="9451b-134">DeviceID</span></span>  <br/> |<span data-ttu-id="9451b-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="9451b-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="9451b-136">A ID do dispositivo é uma GUID gerada aleatoriamente uma vez no dispositivo e enviado ao serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="9451b-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="9451b-137">Os dados do censo NÃO contêm nenhuma informação que identifique a sua organização ou seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9451b-137">Census data DOES NOT contain any information that identifies your organization or users.</span></span> <span data-ttu-id="9451b-138">Confira a [Política de Privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9451b-138">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="9451b-139">Os dados do censo são ativados por padrão e não podem ser desativados por administradores ou usuários finais.</span><span class="sxs-lookup"><span data-stu-id="9451b-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="9451b-140">Dados de uso</span><span class="sxs-lookup"><span data-stu-id="9451b-140">Usage data</span></span>

<span data-ttu-id="9451b-141">Os dados de uso incluem informações como número de chamadas feitas, número de mensagens instantâneas enviadas ou recebidas, número de participação em reuniões, frequência de recursos usados e problemas de estabilidade.</span><span class="sxs-lookup"><span data-stu-id="9451b-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="9451b-142">Os dados de uso podem conter informações que identificam sua organização, como contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9451b-142">Usage data might contain information that identifies your organization, such as contoso.com.</span></span> <span data-ttu-id="9451b-143">Aqui estão alguns exemplos específicos dos dados de uso coletados:</span><span class="sxs-lookup"><span data-stu-id="9451b-143">Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="9451b-144">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9451b-144">**Data type**</span></span>|<span data-ttu-id="9451b-145">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9451b-145">**Example**</span></span>|<span data-ttu-id="9451b-146">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="9451b-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9451b-147">Mensagem Instantânea Enviada</span><span class="sxs-lookup"><span data-stu-id="9451b-147">IM Sent</span></span>  <br/> |<span data-ttu-id="9451b-148">12</span><span class="sxs-lookup"><span data-stu-id="9451b-148">12</span></span>  <br/> ||
|<span data-ttu-id="9451b-149">Mensagem Instantânea Recebida</span><span class="sxs-lookup"><span data-stu-id="9451b-149">IM Received</span></span>  <br/> |<span data-ttu-id="9451b-150">5</span><span class="sxs-lookup"><span data-stu-id="9451b-150">5</span></span>  <br/> ||
|<span data-ttu-id="9451b-151">Participação em reunião (tentativas)</span><span class="sxs-lookup"><span data-stu-id="9451b-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="9451b-152">5</span><span class="sxs-lookup"><span data-stu-id="9451b-152">5</span></span>  <br/> ||
|<span data-ttu-id="9451b-153">Participação em reunião (sucesso)</span><span class="sxs-lookup"><span data-stu-id="9451b-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="9451b-154">4</span><span class="sxs-lookup"><span data-stu-id="9451b-154">4</span></span>  <br/> ||
|<span data-ttu-id="9451b-155">Minutos de chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="9451b-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="9451b-156">30 min</span><span class="sxs-lookup"><span data-stu-id="9451b-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="9451b-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="9451b-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="9451b-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9451b-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="9451b-159">Esse é o nome da organização registrada no Office 365 e é transmitida em texto não criptografado, o que significa que não é ocultado.</span><span class="sxs-lookup"><span data-stu-id="9451b-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="9451b-160">Os dados de uso NÃO contêm nenhuma informação que identifique os usuários.</span><span class="sxs-lookup"><span data-stu-id="9451b-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="9451b-161">A coleta de dados de uso está ativada por padrão, mas os administradores locais podem desativá-la usando a configuração de Política de Grupo DisableAutomaticSendTracing no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9451b-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="9451b-162">Desativar essa configuração afeta todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="9451b-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="9451b-163">Confira [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9451b-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="9451b-164">Os usuários finais não podem ativar ou desativar a coleta de dados de uso.</span><span class="sxs-lookup"><span data-stu-id="9451b-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="9451b-165">Para o Aplicativo Reuniões do Skype e para as páginas da web do iniciador de ingresso, a maneira de controlar a telemetria é por meio desta política:</span><span class="sxs-lookup"><span data-stu-id="9451b-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="9451b-166">Essa política padrão é falsa, portanto, a coleta de telemetria fica desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9451b-166">This policy defaults to false, so telemetry collection is off by default.</span></span> <span data-ttu-id="9451b-167">Essa configuração é por pool e controla todos os usuários que se conectam com o Aplicativo Reuniões do Skype a uma reunião hospedada nesse servidor.</span><span class="sxs-lookup"><span data-stu-id="9451b-167">This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="9451b-168">Dados do relatório de erros</span><span class="sxs-lookup"><span data-stu-id="9451b-168">Error reporting data</span></span>

<span data-ttu-id="9451b-169">Os dados do relatório de erros podem incluir informações sobre desempenho e confiabilidade, configuração do dispositivo, qualidade da conexão de rede, códigos de erro, logs de erro e exceções.</span><span class="sxs-lookup"><span data-stu-id="9451b-169">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions.</span></span> <span data-ttu-id="9451b-170">Aqui estão alguns exemplos específicos de dados do relatórios de erros coletados:</span><span class="sxs-lookup"><span data-stu-id="9451b-170">Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="9451b-171">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9451b-171">**Data type**</span></span>|<span data-ttu-id="9451b-172">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="9451b-172">**Example**</span></span>|<span data-ttu-id="9451b-173">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="9451b-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9451b-174">Direção da mensagem</span><span class="sxs-lookup"><span data-stu-id="9451b-174">Message direction</span></span>  <br/> |<span data-ttu-id="9451b-175">Recebida</span><span class="sxs-lookup"><span data-stu-id="9451b-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="9451b-176">Estado de conversa</span><span class="sxs-lookup"><span data-stu-id="9451b-176">Conversation state</span></span>  <br/> |<span data-ttu-id="9451b-177">Ocioso</span><span class="sxs-lookup"><span data-stu-id="9451b-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="9451b-178">ID do thread de conversa</span><span class="sxs-lookup"><span data-stu-id="9451b-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="9451b-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span><span class="sxs-lookup"><span data-stu-id="9451b-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="9451b-180">UserID</span><span class="sxs-lookup"><span data-stu-id="9451b-180">UserID</span></span>  <br/> |<span data-ttu-id="9451b-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="9451b-181">amosmarble</span></span> <br/> |<span data-ttu-id="9451b-182">A ID é enviada em texto não criptografado, o qual o serviço de telemetria transforma em hash antes de armazená-lo</span><span class="sxs-lookup"><span data-stu-id="9451b-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="9451b-183">Os dados do relatório de erros também podem conter informações de identificação pessoal, como o endereço de IP do usuário e o protocolo SIP Uniform Resource Identifier (SIP URI).</span><span class="sxs-lookup"><span data-stu-id="9451b-183">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI).</span></span> <span data-ttu-id="9451b-184">Confira a [Política de Privacidade do Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) para obter uma explicação detalhada do que é coletado.</span><span class="sxs-lookup"><span data-stu-id="9451b-184">See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="9451b-185">O relatório de erros exige duas coisas:</span><span class="sxs-lookup"><span data-stu-id="9451b-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="9451b-186">A configuração da Política de Grupo DisableAutomaticSendTracing é definida como False no servidor ou no centro de administração do locatário (esse é o estado padrão).</span><span class="sxs-lookup"><span data-stu-id="9451b-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="9451b-187">Confira [Configurar políticas de inicialização do cliente](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9451b-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="9451b-188">Os usuários finais optam individualmente pela guia Geral (clique no ícone de engrenagem ![Um ícone que representa uma engrenagem ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) e a caixa de diálogo **Opções** é aberta com a guia **Geral** exibida) no cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9451b-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![Captura de tela da caixa de seleção da coleta de dados na caixa de diálogo Opções](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="9451b-190">Para o Aplicativo Reuniões do Skype, o MeetingUxEnableTelemetry também controla o relatório de erros, embora, no caso de no Windows, as configurações do Watson controla o carregamento das informações de falhas.</span><span class="sxs-lookup"><span data-stu-id="9451b-190">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info.</span></span> <span data-ttu-id="9451b-191">Não há nenhuma configuração de usuário para o Aplicativo Reuniões do Skype, como você vê na caixa de diálogo do cliente da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9451b-191">There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="9451b-192">Confira [Definir opções Gerais do Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9451b-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="9451b-193">Você pode conferir [Configurar sua rede para o Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) para configurar sua rede.</span><span class="sxs-lookup"><span data-stu-id="9451b-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="9451b-194">Se você estiver usando o Microsoft 365 ou o Office 365 operado pela 21Vianet na China, confira [Configurar sua rede do Skype for Business Online operado pela 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span><span class="sxs-lookup"><span data-stu-id="9451b-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9451b-195">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9451b-195">Related topics</span></span>
[<span data-ttu-id="9451b-196">Disponibilidade de audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="9451b-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
