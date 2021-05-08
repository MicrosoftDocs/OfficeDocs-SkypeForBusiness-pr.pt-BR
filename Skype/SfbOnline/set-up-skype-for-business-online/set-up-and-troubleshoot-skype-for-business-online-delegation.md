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
description: Este artigo explica como configurar e solucionar problemas Skype for Business delegação Online. Este artigo fornece orientações sobre recomendações de instalação, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239820"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar e solucionar problemas de delegação do Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo explica como configurar e solucionar problemas Skype for Business delegação Online. Este artigo fornece orientações sobre recomendações de instalação, práticas recomendadas e etapas de solução de problemas.
  
## <a name="guidelines-and-requirements"></a>Diretrizes e requisitos

### <a name="guidelines-for-delegation"></a>Diretrizes para delegação

Configurar e fazer com que a delegação funcione corretamente depende de você seguir estas diretrizes:
  
- Você deve estar usando o cliente Skype for Business 2015 completo com as atualizações mais recentes ou o cliente Skype for Business 2016 completo.
    
- Você deve estar usando o cliente Outlook 2013 com as atualizações mais recentes ou o Outlook 2016 cliente.
    
- Certifique-se de que o delegador e os computadores delegados tenham um Outlook de email que seja o principal ou o perfil padrão. Esse perfil de email deve conter apenas uma conta.
    
- Skype for Business o representante e o representante devem ser usuários online. Além disso, Exchange Server caixas de correio de cada conta devem estar online ou ambas no local.
    
- Tanto o representante quanto o representante devem estar usando a mesma versão principal do Outlook.
    
- O **valor do atributo EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente. Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo Skype for Business PowerShell Online.
    
- O representante e o representante devem estar Skype for Business e Outlook ao mesmo tempo em estações de trabalho diferentes.
    
- Não há suporte para caixas de correio compartilhadas para a delegação Skype for Business Online. Isso porque a caixa de correio compartilhada não tem a lista de controle de acesso (ACL) **de sendonbehalf.**
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business versão do cliente

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Cliente Básico**| Incompatível |Incompatível
|**Skype for Business 2015**|Compatível | Compatível|
|**Skype for Business 2016**|Compatível | Compatível|

   
### <a name="licensing-requirements"></a>Requisitos de licenciamento

**Enterprise Cenário de licenciamento do E3**

|**Licença**|**Clientes**|**Anotações**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016  <br/> Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016  <br/> |Skype for Business O cliente básico não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E3 com Sistema de Telefonia Office 365 + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016  <br/> Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business O cliente básico não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
**Enterprise Cenário de licenciamento do E5**

|**Licença**|**Clientes**|**Anotações**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016.  <br/> Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016  <br/> |Skype for Business O cliente básico não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E5 mais Office 365 plano de chamada  <br/> |Skype for Business para Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016  <br/> Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business O cliente básico não dá suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar e verificar a delegação

Para configurar a delegação Skype for Business Online, siga estas etapas:
  
### <a name="for-windows-clients"></a>Para Windows clientes

 **Guia Encaminhamento de Chamada**
  
1. Selecione **Opções de**  >  **Ferramentas** De Encaminhamento de Chamada  >  **Configurações**.
    
2. Selecione **Editar membros do meu representante**.
    
3. Selecione **Adicionar**, selecione o representante que você deseja adicionar e selecione **OK**.
    
 **Sem guia Encaminhamento de Chamada**
  
1. Em Outlook, selecione **File**  >  **Account Configurações** Delegate  >  **Access**  >  **Add**.
    
2. Localize e adicione o nome da pessoa que será o representante.
    
3. Selecione o menu **Calendário** e selecione **Editor (pode ler, criar e modificar itens)**.
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac - Lync

 **Guia Encaminhamento de Chamada**
  
- Se o cliente não  tiver uma guia Encaminhamento de Chamada que tenha o link **Editar** meus Membros delegados e o delegador estiver localizado em um computador Mac, o delegador deverá entrar em um computador baseado em Windows para configurar a delegação. Isso porque os clientes Mac não podem fazer conexões MAPI, e isso é um requisito para estabelecer uma delegação Skype for Business de Outlook.
    
### <a name="verify-success"></a>Verificar o sucesso

Se a configuração for bem-sucedida, o representante deverá ver a mensagem You were added as a delegate **for < Name>** message e também que o grupo Pessoas que Eu **Gerencie** Chamadas Para é criado. O delegator deve ver que o grupo **Delegates** foi criado.
  
> [!NOTE]
> As permissões de delegação geralmente aparecem dentro de 30 minutos do processo de instalação. No entanto, esse processo pode levar até 24 horas para ser concluído. 
  
## <a name="troubleshooting"></a>Solução de problemas

### <a name="common-issues"></a>Problemas comuns

- > **Problema 1** A entrada do representante continua a aparecer no grupo **Pessoas que Gerencio** Chamadas para Depois que o representante tiver removido o representante do cliente Outlook.
    
  - > **Resolução 1** No cliente Skype for Business, clique com o botão direito do mouse no representante no grupo **Representantes** e selecione **Remover do Grupo**.
    
- > **Problema 2** Depois que o acesso de representante é concedido por meio do cliente Outlook, nem a mensagem de confirmação nem o grupo **People I Manage Calls For** são exibidos para o representante.
    
  - > **Resolução 2** Remova a delegação do cliente Outlook, aguarde cerca de 15 minutos para replicação e adicione o representante novamente.
    
### <a name="other-common-issues"></a>Outros problemas comuns

- A delegação não funcionará se o limite de 25 delegadores e 25 representantes for excedido.
    
- O Skype for Business cliente Basic não tem suporte.
    
    > [!NOTE]
    > Se você instalar o cliente Skype for Business Basic, ele removerá e quebrará a delegação. 
  
- Se o **valor Status de MAPI** não estiver **OK,** certifique-se de que os valores **SIP** e **SMTP** corresponderão.
    
    > [!NOTE]
    > Pode levar vários minutos para que o status MAPI seja exibido como **OK** depois que você começar a Skype for Business e Outlook.
  
- Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.
    
- MAPI não está disponível. Consulte ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).
    
- A Exchange Online caixa de correio não está acessível por meio do cliente Skype for Business cliente. Se isso ocorrer, execute o teste [de Outlook conectividade](https://testconnectivity.microsoft.com/) para garantir que ele passe.
    
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
