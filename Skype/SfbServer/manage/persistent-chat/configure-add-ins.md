---
title: Configurar suplementos para salas de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumo: Saiba como configurar suplementos para salas de chat Persistent Chat Server na Skype para Business Server 2015.'
ms.openlocfilehash: 4fe6c5fa15118949bd559ddb280ddf56fe41b360
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372696"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurar suplementos para salas de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Aprenda a configurar suplementos para salas de chat Persistent Chat Server no Skype para Business Server 2015.
  
Os suplementos são usados para estender a experiência na sala por meio da associação de URLs com salas de chat. Essas URLs aparecem no painel de extensibilidade da conversa do cliente. Um suplemento típico pode incluir uma URL que aponta para um aplicativo Silverlight que intercepta quando um registrador de cotações é postado em uma sala de bate-papo e mostra o histórico de estoque no painel de extensibilidade. Outros exemplos incluem a URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."
  
 Antes que os usuários possam ver um suplemento em um cliente, você deve adicionar o suplemento à lista de suplementos registrados, e Gerentes ou Criadores de salas de chat precisam associar as salas com os suplementos.
  
> [!NOTE]
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configure suplementos para salas de chat usando o Painel de Controle

Para configurar suplementos para salas de chat usando o Painel de Controle:
  
1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e depois em **Suplemento**.
    
    Para várias implantações de pool de servidor de Chat persistente, selecione o pool apropriado na lista suspensa.
    
4. Na página **Suplementos**, clique em **Novo**.
    
5. Em **Selecionar um serviço**, selecione o serviço correspondente para o pool do servidor de Chat persistente onde você precisa criar o suplemento. Os Suplementos não podem ser movidos de um pool a outro nem compartilhado entre pools diferentes.
    
6. Em **Suplementos novos**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para o novo suplemento.
    
   - Em **URL**, especifique a URL que deve ser associada ao suplemento. As URLs são limitadas aos protocolos http e https.
    
7. Clique em **Confirmar**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configure suplementos usando o Windows PowerShell

Você pode configurar suplementos para salas de chat usando os seguintes cmdlets do Windows PowerShell. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Criar um novo suplemento  <br/> |
|Set-CsPersistentChatAddin  <br/> |Definir configurações para um suplemento existente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperar informações sobre suplementos  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Remover um suplemento  <br/> |
   
### <a name="create-a-new-add-in"></a>Criar um novo suplemento

Você pode criar um novo suplemento usando o cmdlet **New-CsPersistentChatAddin** .
  
Por exemplo, o comando a seguir cria um novo suplemento (com o nome ITPersistentChatAddin) para o pool atl-cs-001.contoso.com. O parâmetro de URL e o valor do parâmetro http://atl-cs-001.contoso.com/itchat especifique o local da página da Web do suplemento:
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Definir configurações para um suplemento existente

Você pode definir configurações para um suplemento existente usando o cmdlet **Set-CsPersistentChatAddIn**. Por exemplo, o seguinte comando modifica a URL atribuída ao suplemento do Chat Persistente ITPersistentChatAddin. Nesse caso, a URL é alterada parahttp://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperar informações sobre suplementos

Você pode obter informações sobre suplementos usando o cmdlet **Get-CsPersistentChatAddin**. Por exemplo, o seguinte comando retorna informações sobre todos os suplementos de Chat Persistente configurados para uso na organização:
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Remover um suplemento

Você pode remover um suplemento usando o cmdlet **Remove-CsPersistentChatAddIn** . Por exemplo, o seguinte comando remove o suplemento do Chat Persistente ITChatAddin encontrado no pool atl-cs-001.contoso.com:
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


