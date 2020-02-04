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
description: Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706476"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Configurar e solucionar problemas de delegação do Skype for Business Online

Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
  
## <a name="guidelines-and-requirements"></a>Diretrizes e requisitos

### <a name="guidelines-for-delegation"></a>Diretrizes de delegação

Configurar e obter a delegação para funcionar corretamente depende das seguintes diretrizes:
  
- Você deve estar usando o cliente completo do Skype for Business 2015 com as atualizações mais recentes ou o Skype for Business 2016 Full Client.
    
- Você deve usar o cliente Outlook 2013 com as atualizações mais recentes ou o cliente do Outlook 2016.
    
- Verifique se o delegador e os computadores delegados têm um perfil de email do Outlook que é o perfil principal ou padrão. Esse perfil de email deve conter apenas uma conta.
    
- O Skype for Business para o delegante e o representante devem ser usuários online. Além disso, as caixas de correio do Exchange Server para cada conta devem estar online ou ambas estar locais.
    
- O delegante e o representante devem usar a mesma versão principal do Outlook.
    
- O valor do atributo **EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente. Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo do PowerShell do Skype for Business online.
    
- Tanto o delegante quanto o representante devem estar conectados ao Skype for Business e ao Outlook ao mesmo tempo em diferentes estações de trabalho.
    
- Caixas de correio compartilhadas não são compatíveis com a delegação do Skype for Business online. Isso ocorre porque a caixa de correio compartilhada não tem a ACL (lista de controle de acesso) do **SendOnBehalf** .
    
### <a name="skype-for-business-client-version-support"></a>Suporte de versão do cliente Skype for Business

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Cliente Lync/Skype for Business Basic**| Incompatível |Incompatível
|**Skype for Business 2015**|Compatível | Compatível|
|**Skype for Business 2016**|Compatível | Compatível|

   
### <a name="licensing-requirements"></a>Requisitos de licenciamento

**Cenário de licenciamento Enterprise E3**

|**Licença**|**Clientes**|**Observações**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> |O cliente Skype for Business Basic não oferece suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E3 com o sistema telefônico do Office 365 + plano do xCalling do Office 365  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> Lync para Mac 2011  <br/> |O cliente Skype for Business Basic não oferece suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
**Cenário de licenciamento Enterprise e5**

|**Licença**|**Clientes**|**Observações**|
|:-----|:-----|:-----|
|Enterprise e5  <br/> |Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016.  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> |O cliente Skype for Business Basic não oferece suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
|Enterprise E5 mais o plano de chamadas do Office 365  <br/> |Skype for Business para Mac 2016  <br/> Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016  <br/> Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016  <br/> Lync para Mac 2011  <br/> |O cliente Skype for Business Basic não oferece suporte à delegação.  <br/> Para clientes Mac, você pode delegar chamadas, mas não reuniões.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Configurar e verificar a delegação

Para configurar a delegação do Skype for Business Online, siga estas etapas:
  
### <a name="for-windows-clients"></a>Para clientes Windows

 **Guia encaminhamento de chamadas**
  
1. Selecione **ferramentas** > **Opções** > **configurações de encaminhamento de chamadas**.
    
2. Selecione **Editar membros de meus representantes**.
    
3. Selecione **Adicionar**, selecione o representante que você deseja adicionar e, em seguida, selecione **OK**.
    
 **Sem guia encaminhamento de chamadas**
  
1. No Outlook, selecione **** > **configurações** > de conta de arquivo**Adicionar****acesso** > ao representante.
    
2. Localize e adicione o nome da pessoa que vai ser o representante.
    
3. Selecione o menu **calendário** e, em seguida, selecione **Editor (pode ler, criar e modificar itens)**.
    
### <a name="for-mac-clients---lync"></a>Para clientes Mac-Lync

 **Guia encaminhamento de chamadas**
  
- Se o cliente não tiver uma guia de **encaminhamento de chamadas** com o link **Editar meus membros do representante** e a delegar estiver localizada em um computador Mac, a delegação precisará se conectar a um computador baseado no Windows para configurar a delegação. Isso ocorre porque os clientes Mac não podem fazer conexões MAPI, e isso é um requisito para estabelecer a delegação do Skype for Business a partir do Outlook.
    
### <a name="verify-success"></a>Verificar o sucesso

Se a configuração for bem-sucedida, o representante deve ver a mensagem **você foi adicionado como um representante para < nome>** mensagem e também que as **pessoas para as quais eu gerencio as chamadas para** o grupo são criadas. A delegação deve ver que o grupo de **representantes** é criado.
  
> [!NOTE]
> As permissões de delegação geralmente aparecem dentro de 30 minutos do processo de instalação. No entanto, esse processo pode levar até 24 horas para ser concluído. 
  
## <a name="troubleshooting"></a>Solução de problemas

### <a name="common-issues"></a>Problemas comuns

- > **Edição 1** A entrada do representante continua sendo exibida nas **pessoas que eu gerencio as chamadas para** o grupo depois que o delegador removeu o representante do cliente do Outlook.
    
  - > **Resolução 1** No cliente Skype for Business, clique com o botão direito do mouse no representante no grupo **representantes** e selecione **remover do grupo**.
    
- > **Problema 2** Após o acesso de representante ser concedido por meio do cliente Outlook, nem a mensagem de confirmação nem as **pessoas que eu gerencio chamadas para** o grupo aparecem para o representante.
    
  - > **Resolução 2** Remova a delegação do cliente do Outlook, aguarde cerca de 15 minutos de replicação e, em seguida, adicione o representante novamente.
    
### <a name="other-common-issues"></a>Outros problemas comuns

- A delegação não funciona se o limite de 25 delegadores e 25 representantes for excedido.
    
- Não há suporte para o cliente Skype for Business Basic.
    
    > [!NOTE]
    > Se você instalar o cliente Skype for Business Basic, ele removerá e interromperá a delegação. 
  
- Se o valor de **status MAPI** não estiver **OK**, certifique-se de que os valores **SIP** e **SMTP** sejam correspondentes.
    
    > [!NOTE]
    > Pode levar alguns minutos para que o status MAPI seja exibido como **OK** após iniciar pela primeira vez o Skype for Business e o Outlook.
  
- Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.
    
- O MAPI não está disponível. Consulte o [erro "MAPI não disponível" no cliente Skype for Business 2016](https://support.microsoft.com/en-us/help/3147130).
    
- A caixa de correio do Exchange Online não está acessível por meio do cliente Skype for Business. Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para ter certeza de que ele passou.
    
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
