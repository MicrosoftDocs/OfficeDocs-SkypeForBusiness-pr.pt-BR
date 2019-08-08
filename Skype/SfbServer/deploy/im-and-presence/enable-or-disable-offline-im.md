---
title: Habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Saiba como habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server.
ms.openlocfilehash: 363f7c54d682dc619417a8d9601c7beafc8283c6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235539"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server
 
Saiba como habilitar ou desabilitar mensagens instantâneas (IM) offline no Skype for Business Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar mensagens instantâneas offline no Skype for Business Server

As mensagens instantâneas offline são um recurso do lado do cliente incorporado ao cliente Skype for Business (2016 C2R Build 16.0.6701.1000 ou superior) que aproveita os serviços Web do Exchange (EWS) para enviar mensagens do cliente Skype for Business para a caixa de correio do Exchange de um usuário. As mensagens INSTANTÂNEAs offline usam o EWS (Exchange Web Services) para enviar mensagens offline do cliente Skype for Business para a caixa de correio do destinatário. O EWS deve estar disponível para o cliente Skype for Business para que as mensagens offline sejam enviadas. Para saber mais sobre como planejar mensagens instantâneas e presença, consulte [planejar mensagens instantâneas e presença no Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Se a caixa de correio do usuário estiver hospedada no Exchange local, será necessário o cliente Skype for Business (2016 C2R Build 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar ou desabilitar mensagens instantâneas offline no Skype for Business Server

1. Abra o Shell de gerenciamento do Skype for Business Server.
    
2. Execute o comando a seguir para habilitar o IM Offline.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > No Skype for Business Server 2015 CU3, a opção EnableOfflineIM é definida como $True por padrão. Para desabilitá-la, defina esse valor como $False. 
  
3. Execute o seguinte comando para confirmar se o recurso armazenar mensagens de chat offline está definido.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integração do IM Offline com o Exchange

O IM Offline não estará disponível para os remetentes se eles tiverem uma política de cliente que desabilite o salvamento automático de mensagens offline na pasta do histórico da conversa (EnableIMAutoArchiving = $false). Não há nenhum mecanismo para verificar se o destinatário é capaz de receber mensagens offline.
  
Para mensagens offline enviadas dentro da mesma organização, elas serão recebidas como uma mensagem de email com classe de mensagem de mensagem instantânea. Note. MissedConversation e será incluído na pasta de **conversa perdida** do Outlook, bem como histórico de conversas que será retirado na guia lista/histórico de conversas recentes dos clientes do Skype for Business.
  
Para mensagens offline enviadas de organização federada, elas serão recebidas como mensagens de email sem IM.Note.MisssedConversation e não serão incluídas nas pastas de histórico da conversa nem de conversas perdidas. 
  
## <a name="troubleshooting"></a>Solução de problemas

Há um temporizador de dois minutos quando uma mensagem offline é enviada quando é retirada e processada. Se não for possível processar mensagens offline, elas aparecerão no seguinte diretório: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

O log de ETL principal do Skype for Business conterá informações sobre o processamento de mensagens offline e será a melhor fonte de investigação/solução de problemas. 
  
> [!NOTE]
> Foi relatado um problema em que as mensagens offline não eram enviadas e a pasta "Rascunhos" era preenchida com mensagens. Isso ocorria em caixas de correio do Exchange no Local. O problema foi resolvido em todos os canais C2R em 14/06/2016.   
