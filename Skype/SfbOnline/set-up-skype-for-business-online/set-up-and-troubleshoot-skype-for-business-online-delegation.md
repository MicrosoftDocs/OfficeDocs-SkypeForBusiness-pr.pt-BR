---
title: Configurar e solucionar problemas de delegação do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business Online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010794"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar e solucionar problemas de delegação do Skype for Business Online

Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business Online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
  
## <a name="guidelines-and-requirements"></a>Diretrizes e requisitos

### <a name="guidelines-for-delegation"></a>Diretrizes para delegação

Configurar e fazer com que a delegação funcione corretamente depende de você seguir estas diretrizes:
  
- Você deve usar o cliente completo do Skype for Business 2015 com as atualizações mais recentes ou o cliente completo do Skype for Business 2016.
    
- Você deve estar usando o cliente outlook 2013 com as atualizações mais recentes ou o cliente do Outlook 2016.
    
- Certifique-se de que o delegador e os computadores delegados tenham um perfil de email do Outlook que seja o perfil principal ou padrão. Esse perfil de email deve conter apenas uma conta.
    
- O Skype for Business para o delegador e o representante devem ser usuários online. Além disso, as caixas de correio do Exchange Server para cada conta devem estar online ou ambas no local.
    
- O delegador e o representante devem estar usando a mesma versão principal do Outlook.
    
- O **valor do atributo EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente. Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo PowerShell do Skype for Business Online.
    
- O delegador e o representante devem estar no Skype for Business e no Outlook ao mesmo tempo em diferentes estações de trabalho.
    
- Não há suporte para caixas de correio compartilhadas para a delegação do Skype for Business Online. Isso porque a caixa de correio compartilhada não tem a lista de controles de acesso (ACL) de **sernbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Suporte à versão do cliente Skype for Business

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Cliente Lync/Skype for Business Basic**| Incompatível |Incompatível
|**Skype for Business 2015**|Compatível | Compatível|
|**Skype for Business 2016**|Compatível | Compatível|

   
### <a name="licensing-requirements"></a>Requisitos de licenciamento

**Cenário de licenciamento enterprise E3**

|**Licença**|**Clientes**|**Anotações**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> |O cliente Skype for Business Basic não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E3 com o Office 365 Phone System + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> Lync para Mac 2011  <br/> |O cliente Skype for Business Basic não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
**Cenário de licenciamento enterprise E5**

|**Licença**|**Clientes**|**Anotações**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |O Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016.  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> |O cliente Skype for Business Basic não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E5 mais Plano de Chamada do Office 365  <br/> |Skype for Business para Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> Lync para Mac 2011  <br/> |O cliente Skype for Business Basic não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar e verificar delegação

Para configurar a delegação do Skype for Business Online, siga estas etapas:
  
### <a name="for-windows-clients"></a>Para clientes windows

 **Guia Encaminhamento de Chamada**
  
1. Selecione **Configurações** de Encaminhamento de Chamada de Opções  >    >  **de Ferramentas.**
    
2. Selecione **Editar membros de meu representante.**
    
3. Selecione **Adicionar,** selecione o representante que você deseja adicionar e, em seguida, selecione **OK.**
    
 **Sem guia Encaminhamento de Chamada**
  
1. No Outlook, selecione **Acesso de** Representante  >  **de Configurações de Conta** de  >    >  **Arquivo.**
    
2. Localize e adicione o nome da pessoa que será o representante.
    
3. Selecione o menu **Calendário** e, em seguida, selecione **Editor (pode ler, criar e modificar itens).**
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac - Lync

 **Guia Encaminhamento de Chamada**
  
- Se o cliente não  tiver uma guia Encaminhamento de Chamada que tenha o **link** Editar meus Membros Delegados e o delegador estiver localizado em um computador Mac, o delegador deverá entrar em um computador baseado no Windows para configurar a delegação. Isso porque os clientes mac não podem fazer conexões MAPI, e esse é um requisito para estabelecer a delegação do Skype for Business do Outlook.
    
### <a name="verify-success"></a>Verificar o sucesso

Se a configuração for bem-sucedida, o representante verá que Você foi adicionado como representante  da mensagem **< Nome>** e também que o grupo Pessoas para quem Eu Gerencie Chamadas foi criado. O delegador deve ver que o grupo **Representantes** é criado.
  
> [!NOTE]
> As permissões de delegação geralmente aparecem dentro de 30 minutos após o processo de configuração. No entanto, esse processo pode levar até 24 horas para ser concluído. 
  
## <a name="troubleshooting"></a>Solução de problemas

### <a name="common-issues"></a>Problemas comuns

- > **Problema 1** A entrada de representante continua a aparecer no grupo **Pessoas para** as que Eu Gerencio Chamadas depois que o delegado remover o representante do cliente do Outlook.
    
  - > **Resolução 1** No cliente Skype for Business, clique com  o botão direito do mouse no representante no grupo Representantes e selecione **Remover do Grupo.**
    
- > **Problema 2** Depois que o acesso de representante é concedido por  meio do cliente do Outlook, nem a mensagem de confirmação nem o grupo Pessoas para quem Eu Gerencio Chamadas são exibidos para o representante.
    
  - > **Resolução 2** Remova a delegação do cliente outlook, aguarde cerca de 15 minutos para replicação e adicione o representante novamente.
    
### <a name="other-common-issues"></a>Outros problemas comuns

- A delegação não funcionará se o limite de 25 delegadores e 25 representantes for excedido.
    
- Não há suporte para o cliente Skype for Business Basic.
    
    > [!NOTE]
    > Se você instalar o cliente Skype for Business Basic, ele removerá e quebrará a delegação. 
  
- Se o **valor status MAPI** não estiver **OK,** certifique-se de que os valores **SIP** e **SMTP** corresponderem.
    
    > [!NOTE]
    > Pode levar vários minutos para que o status MAPI seja exibido como **OK** depois de iniciar o Skype for Business e o Outlook pela primeira vez.
  
- Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.
    
- MAPI não está disponível. Veja [o erro "MAPI indisponível" no cliente Skype for Business 2016.](https://support.microsoft.com/help/3147130)
    
- A caixa de correio do Exchange Online não é acessível por meio do cliente Skype for Business. Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para garantir que ele passe.
    
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
