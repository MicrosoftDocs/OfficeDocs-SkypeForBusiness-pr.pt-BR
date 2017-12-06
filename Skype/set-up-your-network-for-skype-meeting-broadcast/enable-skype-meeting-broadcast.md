---
title: "Habilitar a Transmissão de Reunião do Skype"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Para que as pessoas em sua organização podem usar Transmissão de Reunião do Skype, você precisa ativá-lo. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não souber o Windows PowerShell, considere a possibilidade de contratar um parceiro da Microsoft realizar esta etapa para você."
---

# Habilitar a Transmissão de Reunião do Skype

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](5299cce0-850e-42dc-b6ae-2d0ee775c4a9.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/5299cce0-850e-42dc-b6ae-2d0ee775c4a9). 
  
Para que as pessoas em sua organização podem usar Transmissão de Reunião do Skype, você precisa ativá-lo. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não souber o Windows PowerShell, considere a possibilidade de contratar um [parceiro da Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) realizar esta etapa para você.
  
> [!CAUTION]
> Transmissão de Reunião do Skype está desativado por padrão porque a distribuição do conteúdo de mídia de uma reunião de difusão usa a rede de entrega de conteúdo (CDN) do Microsoft Azure para obter muito alta escala para dar suporte a milhares de pessoas que estão assistindo a uma transmissão. O conteúdo de mídia em partes passando pela CDN está criptografado e o cache CDN tem uma vida útil limitada. Além disso, o componente do Azure CDN pode não atender ainda todos os elementos do modelo da UE cláusulas proveniente a diretiva de proteção de dados da UE. Ao ativar esse recurso, você reconhece este aviso. 
  
## Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business

1. Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. No Centro de Administração do Office 365 vá para **Centros de Administração** > **Skype for Business**.
    
3. Do **Skype para o Centro de administração de negócios**, vá para **reuniões Online** > **transmita reuniões** e selecione **Habilitar transmissão de reunião do Skype**.
    
## Habilitar a Transmissão de Reunião do Skype usando o PowerShell

1. Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Será necessário também instalar o módulo Windows PowerShell para Skype for Business Online, para permitir que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reiniciar o computador se for solicitado.
    
2. No **Menu Iniciar**, escolha **O Windows PowerShell**.
    
3. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
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

    Você pode confirmar que a configuração é ativada executando  `Get-CsBroadcastMeetingConfiguration` novamente.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype. 
  
6. Os usuários agora podem conter transmitir reuniões com outros usuários na sua empresa. Para obtê-los iniciado, aponte para [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## Configurar a rede para transmitir reuniões com participantes externos

Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
Para ignorar esta etapa e em vez disso, adicione outro business sua federação, consulte [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

