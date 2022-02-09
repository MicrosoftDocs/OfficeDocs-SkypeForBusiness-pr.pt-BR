---
title: Configurar Skype for Business Server usar o armazenamento unificado de contatos
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumo: Configure o armazenamento unificado de contatos para Exchange Server e Skype for Business Server.'
ms.openlocfilehash: 41065b6df0e1d313ca986bef7be6bbd1609ab04a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417214"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar Skype for Business Server usar o armazenamento unificado de contatos
 
**Resumo:** Configure o armazenamento unificado de contatos para Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.
  
Usando o armazenamento unificado de contatos, os usuários mantêm uma única lista de contatos e, em seguida, têm esses contatos disponíveis em vários aplicativos, incluindo Skype for Business, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013. Quando você habilita o armazenamento unificado de contatos para um usuário, os contatos desse usuário não são armazenados Skype for Business Server e recuperados conforme necessário. Em vez disso, seus contatos são armazenados no Exchange Server 2016 ou Exchange Server 2013 e são recuperados usando Exchange Web Services.
  
> [!NOTE]
> Tecnicamente, as informações de contato são armazenadas em um par de pastas encontradas na caixa de correio Exchange usuário. Os próprios contatos são armazenados em uma pasta chamada Skype for Business Contatos que fica visível para os usuários finais; os metadados sobre os contatos são armazenados em uma subpasta que não está visível para os usuários finais. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitando o repositório unificado de contatos para um usuário

Se a autenticação de servidor para servidor entre Skype for Business Server e Exchange Server já estiver configurada, você também habilitará o armazenamento unificado de contatos; nenhuma configuração adicional do servidor será necessária. No entanto, será necessária configuração adicional da conta do usuário para transferir os contatos de um usuário para o repositório unificado de contatos. Por padrão, os contatos do usuário são mantidos Skype for Business Server e não no armazenamento unificado de contatos.
  
O acesso ao armazenamento unificado de contatos é gerenciado usando Skype for Business Server de serviços de usuário. As políticas de serviços de usuário têm uma única propriedade (UcsAllowed), que é usada para determinar o local onde os contatos de um usuário são armazenados. Se um usuário for gerenciado por uma política de serviços de usuário na qual UcsAllowed foi definido como True ($True), os contatos do usuário serão armazenados no armazenamento unificado de contatos. Se o usuário for gerenciado por uma política de serviços de usuário na qual UcsAllowed foi definido como False ($False), seus contatos serão armazenados em Skype for Business Server.
  
Quando você instala Skype for Business Server, uma única política de serviços de usuário (configurada no escopo global) também é instalada. O valor UcsAllowed nesta política é definido como True, o que significa que, por padrão, os contatos do usuário serão armazenados no armazenamento unificado de contatos (supondo que isso tenha sido implantado e configurado). Se você deseja migrar todos os seus contatos de usuário para o armazenamento unificado de contatos, não é preciso fazer nada. 
  
Se você preferir não migrar todos os seus contatos para o armazenamento unificado de contatos, poderá desabilitar o armazenamento unificado de contatos para todos os usuários definindo a propriedade UcsAllowed na política global como False:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Depois de desabilitado o armazenamento unificado de contatos na política global, você pode criar uma política por usuário que habilita o uso do armazenamento unificado de contatos; Isso permite que alguns usuários mantenham seus contatos no armazenamento unificado de contatos enquanto outros usuários continuam mantendo seus contatos em Skype for Business Server. Você pode criar uma política de serviços de usuário por usuário usando um comando semelhante a este:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Depois que você tiver criado a nova política, precisará atribuí-la aos usuários que deverão ter acesso ao repositório unificado de contatos. As políticas por usuário podem ser atribuídas aos usuários com o uso de comandos semelhantes ao seguinte:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Depois que a política tiver sido atribuída, Skype for Business Server começará a migrar os contatos do usuário para o armazenamento unificado de contatos. Depois que a migração for concluída, o usuário terá seus contatos armazenados em Exchange em vez de Skype for Business Server. Se o usuário estiver conectado ao Lync 2013 no momento em que a migração for concluída, uma caixa de mensagem aparecerá e ele será solicitado a fazer logon do Skype for Business e fazer logon novamente para finalizar o processo. Os usuários que não foram atribuídos a essa política por usuário não terão seus contatos migrados para o armazenamento unificado de contatos. Isso porque esses usuários estão sendo gerenciados pela política global e o uso do armazenamento unificado de contatos foi desabilitado na política global.
  
Você pode verificar se os contatos de um usuário foram migrados com êxito para o repositório de contatos unificado executando o cmdlet [Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) de dentro do Shell de Gerenciamento do Skype for Business Server:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore tiver êxito, isso significa que os contatos do usuário sip:kenmyer@<span></span>litwareinc.com<span></span> foram migrados para o armazenamento unificado de contatos.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertendo o repositório unificado de contatos

Se você precisar remover os contatos de um usuário do armazenamento unificado de contatos (por exemplo, se o usuário precisar ser reemocupado no Microsoft Lync Server 2010 e, portanto, não puder mais usar o armazenamento unificado de contatos), você deve fazer duas coisas. Primeiro, você deve atribuir ao usuário uma nova política de serviços de usuário, uma que proíbe o armazenamento de contatos no armazenamento unificado de contatos. (Ou seja, uma política em que a propriedade UcsAllowed foi definida como $False.) Se você não tiver essa política, poderá criar uma usando um comando semelhante a este:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Em seguida, você pode atribuir essa nova política por usuário (NoUnifiedContactStore) usando um comando como o seguinte:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

O comando anterior atribui a nova política ao usuário Ken Myer e também impede que os contatos de Ken sejam migrados para o repositório unificado de contatos.
  
> [!NOTE]
> Em alguns casos, você pode obter o mesmo efeito líquido simplesmente desem atribuir a política de serviços de usuário atual do usuário. Por exemplo, suponha que Ken Myer tenha uma política de serviços de usuário por usuário que habilita o repositório unificado de contatos, mas sua política global proíbe o uso do repositório unificado de contatos. Nesse caso, você pode desem atribuir a política de serviços por usuário de Ken. Quando você fizer isso, Ken será automaticamente gerenciado pela política global e deixará de ter acesso ao repositório unificado de contatos. Para desatribuição de uma política atribuída anteriormente por usuário, use o mesmo comando mostrado anteriormente, mas desta vez de definir o parâmetro PolicyName como um valor nulo: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null 
  
É importante lembrar-se da frase "impede que os contatos de Ken sejam migrados para o repositório unificado de contatos" ao trabalhar com o repositório unificado de contatos. Simplesmente atribuir uma nova política de serviços de usuário a Ken não removerá seus contatos do repositório unificado de contatos. Quando um usuário faz o Skype for Business Server, o sistema verifica a política de serviços de usuário do usuário para ver se seus contatos devem ser mantidos no armazenamento unificado de contatos. Se a resposta for sim (ou seja, se a propriedade UcsAllowed estiver definida como $True), esses contatos serão migrados para o repositório unificado de contatos (pressupondo que eles ainda não estejam no repositório unificado de contatos). Se a resposta for não, Skype for Business Server simplesmente ignorará os contatos do usuário e seguirá para sua próxima tarefa. Isso significa que Skype for Business Server moverá automaticamente os contatos de um usuário do armazenamento unificado de contatos, independentemente do valor da propriedade UcsAllowed.
  
Isso também significa que, depois de atribuir ao usuário uma nova política de serviços de usuário, você deve executar o cmdlet [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover os contatos do usuário para fora do Exchange Server e voltar para Skype for Business Server. Por exemplo, após atribuir uma nova política de serviços de usuário a Ken Myer, você poderá remover seus contatos do repositório unificado de contatos usando o seguinte comando:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se você alterar a política de serviços de usuário, mas não executar o cmdlet Invoke-CsUcsRollback, os contatos de Ken não serão removidos do repositório unificado de contatos. E se você executar o Invoke-CsUcsRollback, mas não alterar a política de serviços de usuário de Ken Myer? Nesse caso, os contatos de Ken serão temporariamente removidos do repositório unificado de contatos. É importante atentar ao fato de que essa remoção é temporária. Depois que os contatos de Ken foram removidos do armazenamento unificado de contatos, o Skype for Business Server aguardará 7 dias e verificará qual política de serviços de usuário foi atribuída a Ken. Se uma política que permite o uso do repositório unificado de contatos ainda estiver atribuída a Ken, seus contatos serão automaticamente transferidos de volta para o repositório de contatos. Para remover permanentemente os contatos do repositório unificado de contatos, você precisa alterar a política de serviços de usuário e também executar o cmdlet Invoke-CsUcsRollback.
  
Devido ao grande número de variáveis que podem afetar a migração, é difícil estimar quanto tempo levará para que as contas sejam totalmente migradas para o armazenamento unificado de contatos. Como regra geral, no entanto, a migração não entrará em vigor imediatamente: mesmo ao migrar um pequeno número de contatos, pode levar 10 minutos ou mais antes da conclusão da movimentação.
