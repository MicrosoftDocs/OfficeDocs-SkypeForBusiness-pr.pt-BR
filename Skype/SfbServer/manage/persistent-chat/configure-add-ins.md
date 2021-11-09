---
title: Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumo: saiba como configurar os complementos para salas de chat do Servidor de Chat Persistente Skype for Business Server 2015.'
ms.openlocfilehash: c23a0dd11d51bbfa1c49d8a910decda5be0ac48f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854295"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como configurar os complementos para salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.
  
Os complementos são usados para estender a experiência na sala associando URLs a salas de chat. Essas URLs aparecem no painel de extensibilidade da conversa do cliente. Um complemento típico pode incluir uma URL apontando para um aplicativo Silverlight que intercepta quando um ticker de ações é postado em uma sala de chat e mostra o histórico de ações no painel de extensibilidade. Outros exemplos incluem o URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."
  
 Para que os usuários possam ver um complemento no cliente, você deve adicionar o add-in à lista de complementos registrados, e os Gerentes de sala de chat ou Criadores precisam associar salas ao complemento.
  
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurar os complementos para salas de chat usando o Painel de Controle

Para configurar os complementos para salas de chat usando o Painel de Controle:
  
1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Suplemento**.
    
    Para várias implantações de pool do Servidor de Chat Persistente, selecione o pool apropriado na listada.
    
4. Na página **Suplementos**, clique em **Novo**.
    
5. Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool do Servidor de Chat Persistente onde você precisa criar o Add-in. Os suplementos não podem ser movidos de um pool para outro ou compartilhado entre pools diferentes.
    
6. Em **Suplementos novos**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para o novo suplemento.
    
   - Em **URL**, especifique o  URL que deve ser associada ao suplemento. AS URLs são limitadas aos protocolos http e https.
    
7. Clique em **Confirmar**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurar os complementos usando Windows PowerShell

Você pode configurar os complementos para salas de chat usando os seguintes Windows PowerShell cmdlets. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte Skype for Business Server Shell de Gerenciamento [2015](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Criar um novo complemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurar configurações para um complemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperar informações sobre os complementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Remover um complemento  <br/> |
   
### <a name="create-a-new-add-in"></a>Criar um novo complemento

Você pode criar um novo Add-in usando o cmdlet **New-CsPersistentChatAddin.**
  
Por exemplo, o comando a seguir cria um novo complemento (com o nome ITPersistentChatAddin) para o pool `atl-cs-001.contoso.com` . O parâmetro URL e o valor do parâmetro `http://atl-cs-001.contoso.com/itchat` especificam o local da página da Web do complemento:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurar configurações para um complemento existente

Você pode definir configurações para um complemento existente usando o cmdlet **Set-CsPersistentChatAddIn.** Por exemplo, o comando a seguir modifica a URL atribuída ao complemento de Chat Persistente ITPersistentChatAddin. Nesse caso, a URL é alterada para `http://atl-cs-001.contoso.com/itchat2` :
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperar informações sobre os complementos

Você pode obter informações sobre os complementos usando o cmdlet **Get-CsPersistentChatAddin.** Por exemplo, o comando a seguir retorna informações sobre todos os complementos de Chat Persistente configurados para uso na organização:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Remover um complemento

Você pode remover um Add-in usando o cmdlet **Remove-CsPersistentChatAddIn.** Por exemplo, o comando a seguir remove o complemento de Chat Persistente ITChatAddin encontrado no pool `atl-cs-001.contoso.com` :
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


