---
title: "Habilitar a Transmissão de Reunião do Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "Antes das pessoas na sua organização podem usar a transmissão do Skype reunião, é necessário habilitá-lo. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um Parceiro Microsoft para realizar essa etapa para você."
ms.openlocfilehash: a220f6809aec764b4ad83ca49926dcc919a8fbe3
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2018
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar a Transmissão de Reunião do Skype

Antes das pessoas na sua organização podem usar a transmissão do Skype reunião, é necessário habilitá-lo. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
> [!CAUTION]
> Transmissão do Skype reunião está desativado por padrão, porque a distribuição do conteúdo de uma reunião de transmissão mídia usa a rede de entrega de conteúdo (CDN) do Microsoft Azure para atingir escala muito alta para dar suporte a milhares de pessoas assistindo a uma transmissão. O conteúdo de mídia fragmentada passem pela CDN é criptografado e o cache CDN tem uma vida útil limitada. Além disso, o componente do Windows Azure CDN pode não atender ainda elementos todas as cláusulas de modelo da UE lematização da diretiva de proteção de dados da UE. Ao habilitar esse recurso, você reconhece este aviso. 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business

1. Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. No Centro de Administração do Office 365 vá para **Centros de Administração** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, vá para **reuniões Online** > **reuniões de difusão**e selecione **Habilitar transmissão de reunião do Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar a Transmissão de Reunião do Skype usando o PowerShell

1. Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
2. No **Menu Iniciar**, escolha o **Windows PowerShell**.
    
3. Na janela do **Windows PowerShell**, conecte-se à sua organização do Office 365 executando:
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. Confirme sua configuração do Transmissão de Reunião do Skype atual executando:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Habilite o Transmissão de Reunião do Skype para sua organização executando:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Você pode confirmar que a configuração é habilitada executando `Get-CsBroadcastMeetingConfiguration` novamente.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype. 
  
6. Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar a rede para transmitir reuniões com participantes externos

Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Tópicos relacionados

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

## <a name="feedback"></a>Comentários?
Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).