---
title: Configurar o Skype for Business Server para usar o repositório unificado de contatos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumo: Configure o repositório unificado de contatos para Exchange Server e do Skype para Business Server.'
ms.openlocfilehash: e71ba6b19ce0800e8a160a7cadce3c6cdea5a1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894243"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar o Skype for Business Server para usar o repositório unificado de contatos
 
**Resumo:** Configure o repositório unificado de contatos para o Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.
  
Usando o repositório unificado de contatos, os usuários mantém uma lista de contatos único e então tem esses contatos disponíveis em vários aplicativos, incluindo Skype para negócios, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando você habilita o repositório unificado de contatos para um usuário, os contatos do usuário não estiverem armazenados no Skype para Business Server e recuperados conforme necessário. Em vez disso, seus contatos são armazenados no Exchange Server 2016 ou Exchange Server 2013 e serão recuperados usando serviços Web do Exchange.
  
> [!NOTE]
> Tecnicamente, informações de contato são armazenadas em um par de pastas encontradas na caixa de correio do Exchange do usuário. Os contatos sozinhos são armazenados em uma pasta denominada Skype para contatos comerciais que é visível aos usuários finais; metadados sobre os contatos são armazenados em uma subpasta que não é visível aos usuários finais. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitando o repositório unificado de contatos para um usuário

Se a autenticação de servidor-para-servidor entre o Skype para Business Server e o Exchange Server já está configurada, então você também tenha habilitado o armazenamento unificado de contatos; Nenhuma configuração de servidor adicional é necessária. No entanto, será necessária configuração adicional da conta do usuário para transferir os contatos de um usuário para o repositório unificado de contatos. Por padrão, os contatos do usuário são mantidos no Skype para Business Server e não no repositório unificado de contatos.
  
Acesso ao repositório unificado de contatos é gerenciado por meio de Skype para políticas de serviços de usuário do servidor de negócios. As políticas de serviços de usuário têm uma única propriedade (UcsAllowed), que é usada para determinar o local onde os contatos de um usuário são armazenados. Se um usuário é gerenciado por uma política de serviços do usuário cuja UcsAllowed tiver sido definida como True ($True), em seguida, os contatos do usuário serão armazenados no repositório unificado de contatos. Se o usuário é gerenciado por um usuário onde UcsAllowed tiver sido definida como False ($False) e seus contatos serão armazenados no Skype para Business Server de política de serviços.
  
Quando você instala o Skype para Business Server, uma política de serviços de usuário único (configurada no escopo global) também é instalada. O valor de UcsAllowed nessa política é definido como True, o que significa que, por padrão, os contatos do usuário serão colocados no repositório unificado de contatos (presumindo que ele tenha sido implantado e configurado). Se você quiser migrar todos os seus contatos de usuário para o repositório unificado de contatos,não será necessário fazer nada. 
  
Se você preferir não migrar todos os contatos para o repositório unificado de contatos, desabilite esse repositório para todos os usuários configurando a propriedade UcsAllowed na política global como False:
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Depois que você desabilitou o armazenamento unificado de contatos na política global você pode criar uma política por usuário que permite o uso do repositório unificado de contatos; Isso permite que você tenha alguns usuários manter seus contatos no repositório unificado de contatos, enquanto outros usuários continuam manter seus contatos no Skype Business Server. É possível criar uma política de serviços de usuário por usuário utilizando um comando como este:
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Depois de criar a nova política, você terá que atribuí-la aos usuários que devem ter acesso ao repositório unificado de contatos. As políticas por usuário podem ser atribuídas aos usuários com o uso de comandos semelhantes ao seguinte:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Depois que tiver sido atribuída a política, Skype para Business Server irá começar a migrar os contatos do usuário para o repositório unificado de contatos. Após a migração estiver concluída, o usuário terá seus contatos armazenados no Exchange, em vez do Skype para Business Server. Se o usuário acontece ter feito logon em Lync 2013 na migração de tempo for concluído, será exibida uma caixa de mensagem e ele será solicitado a faça logout Skype para negócios e, em seguida, logon novamente para finalizar o processo. Os usuários que não tiverem recebido essa política por usuário não terão seus contatos migrados para o repositório unificado de contatos. Isso acontece porque os usuários que estão sendo gerenciados pela política global e uso do repositório unificado de contatos tiver sido desabilitado na política global.
  
Você pode verificar que os contatos de um usuário com êxito foram migrados para o armazenamento unificado de contatos executando o cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) do dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore for bem-sucedido, significa que os contatos para o usuário sip: kenmyer @<span></span>litwareinc<span></span>.com foram migrados para o armazenamento unificado de contatos.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertendo o repositório unificado de contatos

Se você precisar remover contatos do usuário do repositório unificado de contatos, (por exemplo, se o usuário precisa ser colocados no Microsoft Lync Server 2010 e, portanto, não poderá mais usar o repositório unificado de contatos), você deve fazer duas coisas. Primeiro, você deve atribuir ao usuário uma nova política de serviços do usuário, que proíbe o armazenamento de contatos no repositório unificado de contatos. (Ou seja, uma política de onde a propriedade UcsAllowed tiver sido definido como $False.) Se você não tiver dessas diretivas, você pode criar uma usando um comando semelhante a esta:
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Em seguida, você pode atribuir essa nova política por usuário (NoUnifiedContactStore) usando um comando como o seguinte:
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

O comando anterior atribui a nova política ao usuário Ken Myer e também impede que os contatos de Ken sejam migrados para o repositório unificado de contatos.
  
> [!NOTE]
> Em alguns casos, é possível obter o mesmo efeito simplesmente cancelando a atribuição da política de serviços de usuário atual do usuário. Por exemplo, suponha que Ken Myer tenha uma política de serviços de usuário por usuário que habilita o repositório unificado de contatos, mas sua política global proíbe o uso do repositório unificado de contatos. Nesse caso, você pode cancelar a atribuição da política de serviços por usuário de Ken. Quando você fizer isso, Ken será automaticamente gerenciado pela política global e deixará de ter acesso ao repositório unificado de contatos. A política de cancelar a atribuição de um atribuído anteriormente por usuário, use o mesmo comando, conforme mostrado antes, mas desta vez defina o parâmetro PolicyName como um valor nulo: Grant-CsUserServicesPolicy-Identity "Ken Myer" - PolicyName $Null 
  
É importante lembrar-se da frase "impede que os contatos de Ken sejam migrados para o repositório unificado de contatos" ao trabalhar com o repositório unificado de contatos. Simplesmente atribuir uma nova política de serviços de usuário a Ken não removerá seus contatos do repositório unificado de contatos. Quando um usuário faz logon no Skype para Business Server, o sistema verifica a política de serviços de usuário do usuário para ver se seus contatos devem ser mantidos no repositório unificado de contatos. Se a resposta for sim (ou seja, se a propriedade UcsAllowed estiver definida como $True), esses contatos serão migrados para o repositório unificado de contatos (pressupondo que eles ainda não estejam no repositório unificado de contatos). Se a resposta for não, em seguida, Skype para Business Server simplesmente ignora os contatos do usuário e prossegue para sua próxima tarefa. Isso significa que Skype para Business Server não avançará automaticamente contatos do usuário quando estou fora do repositório unificado de contatos, independentemente do valor da propriedade UcsAllowed.
  
Isso também significa que, depois de atribuir ao usuário uma nova política de serviços do usuário, você deve executar o cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover os contatos do usuário sair do Exchange Server e voltar ao Skype para Business Server. Por exemplo, após atribuir uma nova política de serviços de usuário a Ken Myer, você poderá remover seus contatos do repositório unificado de contatos usando o seguinte comando:
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se você alterar a política de serviços de usuário, mas não executar o cmdlet Invoke-CsUcsRollback, os contatos de Ken não serão removidos do repositório unificado de contatos. E se você executar o Invoke-CsUcsRollback, mas não alterar a política de serviços de usuário de Ken Myer? Nesse caso, os contatos de Ken serão temporariamente removidos do repositório unificado de contatos. É importante atentar ao fato de que essa remoção é temporária. Depois de contatos de Ken foram removidos do repositório unificado de contatos, Skype para Business Server aguardará 7 dias e verifica qual política de serviços de usuário tenha sido atribuída a Ken. Se uma política que permite o uso do repositório unificado de contatos ainda estiver atribuída a Ken, seus contatos serão automaticamente transferidos de volta para o repositório de contatos. Para remover permanentemente os contatos do repositório unificado de contatos, você precisa alterar a política de serviços de usuário e também executar o cmdlet Invoke-CsUcsRollback.
  
Devido ao grande número de variáveis que podem afetar a migração, é difícil estimar o tempo que será necessário para que todas as contas sejam totalmente migradas para o repositório unificado de contatos. No entanto, como regra geral, a migração não tem efeito imediato: até mesmo a migração de um pequeno número de contatos poderá demorar 10 minutos ou mais para ser concluída.
  

