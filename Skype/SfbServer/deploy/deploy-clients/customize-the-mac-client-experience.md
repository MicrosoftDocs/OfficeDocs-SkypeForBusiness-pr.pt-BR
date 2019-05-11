---
title: Personalizar a experiência do cliente Mac no Skype for Business
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: Este artigo descreve as preferências e os padrões do cliente disponíveis para o cliente do Skype for Business no Mac e como editá-los de fora do aplicativo.
ms.openlocfilehash: ac398ec928ac4f00b107a2fb9bff1dda8e65cd68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893487"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="1bda7-103">Personalizar a experiência do cliente Mac no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1bda7-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="1bda7-104">Este artigo descreve as preferências e os padrões do cliente disponíveis para o cliente do Skype for Business no Mac e como editá-los de fora do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1bda7-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="1bda7-105">Configurações de preferência do cliente Skype for Business para Mac</span><span class="sxs-lookup"><span data-stu-id="1bda7-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="1bda7-106">Determinados recursos e comportamentos que estão disponíveis para Skype para negócios nos clientes Mac são determinados pelas configurações de preferência no cliente.</span><span class="sxs-lookup"><span data-stu-id="1bda7-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="1bda7-107">O Skype para negócios preferências de Mac são encontradas em um arquivo localizado em Macs que instalaram o Skype para o cliente de negócios, localizada no seguinte caminho:</span><span class="sxs-lookup"><span data-stu-id="1bda7-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="1bda7-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="1bda7-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="1bda7-109">Para definir essas preferências, obtenha um prompt de terminal no Mac do cliente e conforme necessário insira padrões com.microsoft.SkypeForBusiness principais comandos de gravação usando as teclas de preferência descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1bda7-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="1bda7-110">**Chaves de preferência do cliente**</span><span class="sxs-lookup"><span data-stu-id="1bda7-110">**Client preference keys**</span></span>


| <span data-ttu-id="1bda7-111">Chave</span><span class="sxs-lookup"><span data-stu-id="1bda7-111">Key</span></span> | <span data-ttu-id="1bda7-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="1bda7-112">Type</span></span> | <span data-ttu-id="1bda7-113">Valor</span><span class="sxs-lookup"><span data-stu-id="1bda7-113">Value</span></span> | <span data-ttu-id="1bda7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1bda7-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bda7-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="1bda7-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="1bda7-116">Bool</span><span class="sxs-lookup"><span data-stu-id="1bda7-116">Bool</span></span>    |<span data-ttu-id="1bda7-117">0 = configuração manual do servidor</span><span class="sxs-lookup"><span data-stu-id="1bda7-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="1bda7-118">1 = detecção automática do servidor (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bda7-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="1bda7-119">Especifique como o Skype para negócios identifica o transporte e o servidor a ser usado durante a entrada.</span><span class="sxs-lookup"><span data-stu-id="1bda7-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="1bda7-120">Se você habilitar essa configuração de política, deverá especificar **internalAutoDiscoveryURL** e **externalAutoDiscoveryURL**.</span><span class="sxs-lookup"><span data-stu-id="1bda7-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="1bda7-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="1bda7-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="1bda7-122">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-122">String</span></span>    |<span data-ttu-id="1bda7-123">URL completa de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="1bda7-123">Full autodiscover URL</span></span>    |<span data-ttu-id="1bda7-124">URL interna de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="1bda7-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="1bda7-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="1bda7-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="1bda7-126">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-126">String</span></span>    |<span data-ttu-id="1bda7-127">URL completa de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="1bda7-127">Full autodiscover URL</span></span>    |<span data-ttu-id="1bda7-128">URL externa de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="1bda7-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="1bda7-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="1bda7-129">httpProxyDomain</span></span>    |<span data-ttu-id="1bda7-130">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-130">String</span></span>    ||<span data-ttu-id="1bda7-131">Domínio do Proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="1bda7-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="1bda7-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="1bda7-132">httpProxyUserName</span></span>    |<span data-ttu-id="1bda7-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-133">String</span></span>    ||<span data-ttu-id="1bda7-134">Nome de usuário do Proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="1bda7-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="1bda7-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="1bda7-135">httpProxyPassword</span></span>    |<span data-ttu-id="1bda7-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-136">String</span></span>    ||<span data-ttu-id="1bda7-137">Senha do Proxy HTTP</span><span class="sxs-lookup"><span data-stu-id="1bda7-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="1bda7-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="1bda7-138">trustedDomainList</span></span>    |<span data-ttu-id="1bda7-139">Matriz</span><span class="sxs-lookup"><span data-stu-id="1bda7-139">Array</span></span>    ||<span data-ttu-id="1bda7-140">Lista de domínios confiáveis ​​para redirecionamentos HTTP.</span><span class="sxs-lookup"><span data-stu-id="1bda7-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="1bda7-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="1bda7-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="1bda7-142">Número</span><span class="sxs-lookup"><span data-stu-id="1bda7-142">Number</span></span>    |<span data-ttu-id="1bda7-143">300 (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bda7-143">300 (default)</span></span>    |<span data-ttu-id="1bda7-144">Tempo limite de Autenticação Automática para usuários sem Histórico da Conversa do Servidor.</span><span class="sxs-lookup"><span data-stu-id="1bda7-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="1bda7-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="1bda7-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="1bda7-146">Bool</span><span class="sxs-lookup"><span data-stu-id="1bda7-146">Bool</span></span>    |<span data-ttu-id="1bda7-147">0 = Desabilitado</span><span class="sxs-lookup"><span data-stu-id="1bda7-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="1bda7-148">1 = Habilitado</span><span class="sxs-lookup"><span data-stu-id="1bda7-148">1 = Enabled</span></span>    |<span data-ttu-id="1bda7-149">Avisa o usuário ao discar um número de emergência de um local desconhecido.</span><span class="sxs-lookup"><span data-stu-id="1bda7-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="1bda7-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="1bda7-150">sipAddress</span></span>    |<span data-ttu-id="1bda7-151">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-151">String</span></span>    ||<span data-ttu-id="1bda7-152">O endereço do SIP (Email) usado para entrar no Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1bda7-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="1bda7-153">userName</span><span class="sxs-lookup"><span data-stu-id="1bda7-153">userName</span></span>    |<span data-ttu-id="1bda7-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1bda7-154">String</span></span>    ||<span data-ttu-id="1bda7-155">O UPN (nome de usuário) usado para entrar no Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1bda7-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="1bda7-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="1bda7-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="1bda7-157">Bool</span><span class="sxs-lookup"><span data-stu-id="1bda7-157">Bool</span></span>    |<span data-ttu-id="1bda7-158">0 = exibem o campo nome do usuário na tela principal entrar e na caixa de diálogo Propriedades avançadas</span><span class="sxs-lookup"><span data-stu-id="1bda7-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="1bda7-159">1 = exibir o campo de nome de usuário somente na caixa de diálogo Propriedades avançadas (padrão)</span><span class="sxs-lookup"><span data-stu-id="1bda7-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="1bda7-160">Especifique onde o campo nome de usuário é exibido durante a entrada.</span><span class="sxs-lookup"><span data-stu-id="1bda7-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="1bda7-161">Exemplos de uso</span><span class="sxs-lookup"><span data-stu-id="1bda7-161">Usage examples</span></span>

<span data-ttu-id="1bda7-162">Para adicionar um único domínio (Contoso.com) à lista de domínios confiáveis você usaria a chave trustedDomainList, conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="1bda7-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="1bda7-163">padrões de gravação com.microsoft.SkypeForBusiness trustedDomainList-matriz-adicionar "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="1bda7-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="1bda7-164">Para adicionar diversos domínios à lista de domínios confiáveis, você usaria a chave trustedDomainList conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="1bda7-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="1bda7-165">padrões de gravação com.microsoft.SkypeForBusiness trustedDomainList-matriz-adicionar "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="1bda7-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="1bda7-166">Exemplo de configurações não editadas</span><span class="sxs-lookup"><span data-stu-id="1bda7-166">Sample unedited settings</span></span>

<span data-ttu-id="1bda7-167">Para referência, aqui está um arquivo de configurações de exemplo usando somente configurações padrão: </span><span class="sxs-lookup"><span data-stu-id="1bda7-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
