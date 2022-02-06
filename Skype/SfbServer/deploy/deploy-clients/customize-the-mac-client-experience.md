---
title: Personalizar a experiência do cliente Mac no Skype for Business
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: Este artigo descreve as preferências e os padrões do cliente disponíveis para o Skype for Business no cliente Mac e como editá-los de fora do Aplicativo.
---

# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Personalizar a experiência do cliente Mac no Skype for Business
 
Este artigo descreve as preferências e os padrões do cliente disponíveis para o Skype for Business no cliente Mac e como editá-los de fora do Aplicativo.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Skype for Business configurações de preferência do cliente Mac

Determinados recursos e comportamentos que estão disponíveis para Skype for Business clientes Mac são determinados pelas configurações de preferência no cliente. As Skype for Business no Mac são encontradas em um arquivo localizado em Macs que instalou o cliente Skype for Business localizado no seguinte caminho: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
Para definir essas preferências, vá para um prompt de terminal no Mac do cliente e, conforme necessário, insira os comandos de teclas write com.microsoft.SkypeForBusiness usando as teclas de preferência descritas na tabela a seguir.
  
**Chaves de preferência do cliente**


| Chave | Tipo | Valor | Descrição |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Bool    |0 = configuração manual do servidor  <br/> 1 = detecção automática de servidor (padrão)    |Especifique como Skype for Business identifica o transporte e o servidor a ser usado durante a login. Se você habilitar essa configuração de política, deverá especificar **internalAutoDiscoveryURL** e **externalAutoDiscoveryURL**.   |
|internalAutoDiscoveryURL    |String    |URL de descoberta automática completa    |URL de descoberta automática interna    |
|externalAutoDiscoveryURL    |Cadeia de caracteres    |URL de descoberta automática completa    |URL de descoberta automática externa    |
|httpProxyDomain    |String    ||Domínio proxy HTTP    |
|httpProxyUserName    |String    ||Nome de usuário de proxy HTTP    |
|httpProxyPassword    |String    ||Senha de proxy HTTP    |
|trustedDomainList    |Matriz    ||Lista de domínios confiáveis para redirecionamentos HTTP.    |
|autoAcceptTimeout    |Número    |300 (padrão)    |Tempo de tempo de aceitação automática para usuários sem Histórico de Conversas do lado do servidor.    |
|warnWhenUnknownLocationForE911    |Bool    |0 = Desabilitado  <br/> 1 = Habilitado    |Avisa o usuário ao discar um número de emergência de um local desconhecido.    |
|sipAddress    |String    ||O endereço SIP (Email) usado para entrar Skype for Business.    |
|userName    |Cadeia de caracteres    ||O UPN (UserName) usado para entrar Skype for Business.    |
|userNameInAdvancedOnly    |Bool    |0 = exibir o campo Nome de Usuário na tela de entrada principal e na caixa de diálogo Propriedades Avançadas  <br/> 1 = exibir o campo Nome de Usuário somente na caixa de diálogo Propriedades Avançadas (padrão)    |Especifique onde o campo Nome de Usuário é exibido durante a assinatura.    |
   
### <a name="usage-examples"></a>Exemplos de uso

Para adicionar um único domínio (Contoso.com) à lista de domínios confiáveis, você usaria a chave trustedDomainList conforme mostrado:
  
padrões de gravação com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"
  
Para adicionar vários domínios à lista de domínios confiáveis, você usaria a chave trustedDomainList conforme mostrado:
  
defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>Exemplo de configurações não iditadas

Para referência, aqui está um arquivo de configurações de exemplo usando apenas configurações padrão: 
  
```console
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
