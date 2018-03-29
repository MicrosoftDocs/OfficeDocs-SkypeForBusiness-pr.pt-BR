---
title: Habilitar ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar ou desabilitar Offline as mensagens Instantâneas no Skype para Business Server 2015.
ms.openlocfilehash: a9133ad82e4d25fae2aebd266273ecbb37c2a010
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline no Skype for Business Server 2015
 
Aprenda a habilitar ou desabilitar Offline as mensagens Instantâneas no Skype para Business Server 2015.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar mensagens instantâneas Offline (IM) em Skype para Business Server 2015

Mensagens Instantâneas offline são um recurso do lado cliente incorporado ao Skype para o cliente de negócios (2016 C2R build 16.0.6701.1000 ou superior) que aproveita os serviços de Web do Exchange (EWS) para enviar mensagens do Skype para o cliente de negócios, caixa de correio do Exchange do usuário. Offline IM usa serviços Web do Exchange (EWS) para enviar mensagens Offline do Skype para o cliente de negócios para a caixa de correio do destinatário. EWS deve estar disponível para o Skype para o cliente de negócios para mensagens Offline a serem enviadas. Para saber mais sobre o planejamento de mensagens instantâneas e presença, consulte [Planejar a mensagens instantâneas e presença no Skype para Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Se a caixa de correio do usuário está hospedada no Exchange local, o Skype para o cliente de negócios (2016 C2R build 16.0.6920.1000) é necessária 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a>Para habilitar ou desabilitar Offline mensagens Instantâneas no Skype para negócios 2015 de servidor com CU3

1. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
2. Execute o comando a seguir para habilitar o IM Offline.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > No Skype para Business Server 2015 CU3, a opção de EnableOfflineIM é definida como $True, por padrão. Para desabilitá-la, defina esse valor como $False. 
  
3. Execute o seguinte comando para confirmar a capacidade de armazenar Offline IM estiver definida.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integração do IM Offline com o Exchange

O IM Offline não estará disponível para os remetentes se eles tiverem uma política de cliente que desabilite o salvamento automático de mensagens offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false). Não há nenhum mecanismo para verificar se o destinatário é capaz de receber mensagens offline.
  
Para Offline mensagens enviadas dentro da mesma organização que eles serão recebidos como uma mensagem de email com a classe de mensagem das mensagens Instantâneas. Note.MissedConversation e será incluído na pasta do Outlook **Conversas perdidas** , bem como histórico da conversa que será obtido no guia de histórico de lista/conversa recente do Skype para clientes corporativos.
  
Para mensagens offline enviadas de organização federada, elas serão recebidas como mensagens de email sem IM.Note.MisssedConversation e não serão incluídas nas pastas de histórico da conversa nem de conversas perdidas. 
  
## <a name="troubleshooting"></a>Solução de problemas

Não há um timer minuto dois quando uma mensagem offline é enviado a quando ele tem buscadas e processadas. Se mensagens offline não podem ser processadas, eles aparecerão no seguinte diretório: 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

O Skype principal para o log de negócios ETL irá conter informações sobre o processamento de mensagens Offline e é a melhor fonte para solução de problemas/investigação. 
  
> [!NOTE]
> Foi relatado um problema em que as mensagens offline não eram enviadas e a pasta "Rascunhos" era preenchida com mensagens. Isso ocorria em caixas de correio do Exchange no Local. O problema foi resolvido em todos os canais C2R em 14/06/2016.  
  

