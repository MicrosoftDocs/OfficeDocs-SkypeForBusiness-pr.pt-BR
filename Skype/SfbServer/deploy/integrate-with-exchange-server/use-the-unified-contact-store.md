---
title: Configurar o Skype for Business Server para usar o repositório unificado de contatos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Resumo: configurar o repositório de contatos unificado do Exchange Server e do Skype for Business Server.'
ms.openlocfilehash: 1719b8e8e5d99b8ef24da32111b69b1f9f847538
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796992"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurar o Skype for Business Server para usar o repositório unificado de contatos
 
**Resumo:** Configurar o repositório de contatos unificado para o Exchange Server 2016 ou o Exchange Server 2013 e o Skype for Business Server.
  
Usando o repositório de contatos unificado, os usuários mantêm uma única lista de contatos e têm esses contatos disponíveis em vários aplicativos, incluindo o Skype for Business, o Microsoft Outlook 2013 e o Microsoft Outlook Web App 2013. Quando você habilita o repositório de contatos unificado para um usuário, os contatos desse usuário não são armazenados no Skype for Business Server e recuperados conforme necessário. Em vez disso, seus contatos são armazenados no Exchange Server 2016 ou no Exchange Server 2013 e são recuperados usando os serviços Web do Exchange.
  
> [!NOTE]
> Tecnicamente, as informações de contato são armazenadas em um par de pastas encontradas na caixa de correio do Exchange do usuário. Os contatos propriamente ditos são armazenados em uma pasta denominada contatos do Skype for Business, que é visível para os usuários finais; metadados sobre os contatos são armazenados em uma subpasta que não está visível para os usuários finais. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitando o repositório unificado de contatos para um usuário

Se a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server já estiver configurada, você também habilitou o repositório de contatos unificado; nenhuma configuração adicional do servidor é necessária. No entanto, será necessária configuração adicional da conta do usuário para transferir os contatos de um usuário para o repositório unificado de contatos. Por padrão, os contatos do usuário são mantidos no Skype for Business Server e não no repositório de contatos unificado.
  
O acesso ao repositório de contatos unificado é gerenciado usando as políticas de serviços de usuário do Skype for Business Server. As políticas de serviços de usuário têm uma única propriedade (UcsAllowed), que é usada para determinar o local onde os contatos de um usuário são armazenados. Se um usuário for gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como true ($True), os contatos do usuário serão armazenados no repositório de contatos unificado. Se o usuário for gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como falso ($False), seus contatos serão armazenados no Skype for Business Server.
  
Quando você instala o Skype for Business Server, uma única política de serviços de usuário (configurada no escopo global) também é instalada. O valor de UcsAllowed nessa política é definido como True, o que significa que, por padrão, os contatos do usuário serão colocados no repositório unificado de contatos (presumindo que ele tenha sido implantado e configurado). Se você quiser migrar todos os seus contatos de usuário para o repositório unificado de contatos,não será necessário fazer nada. 
  
Se você preferir não migrar todos os contatos para o repositório unificado de contatos, desabilite esse repositório para todos os usuários configurando a propriedade UcsAllowed na política global como False:
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Depois de desabilitar o repositório de contatos unificado na política global, você pode criar uma política por usuário que permite o uso do repositório de contatos unificado; Isso permite que alguns usuários mantenham seus contatos no repositório de contatos unificado enquanto outros usuários continuam a manter seus contatos no Skype for Business Server. É possível criar uma política de serviços de usuário por usuário utilizando um comando como este:
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Depois de criar a nova política, você terá que atribuí-la aos usuários que devem ter acesso ao repositório unificado de contatos. As políticas por usuário podem ser atribuídas aos usuários com o uso de comandos semelhantes ao seguinte:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Após a atribuição da política, o Skype for Business Server começará a migrar os contatos do usuário para o repositório de contatos unificado. Após a conclusão da migração, o usuário terá seus contatos armazenados no Exchange, em vez do Skype for Business Server. Se o usuário estiver conectado ao Lync 2013 durante a conclusão da migração, uma caixa de mensagem será exibida e ele será solicitado a se desconectar do Skype for Business e, em seguida, conectar-se novamente para finalizar o processo. Os usuários que não tiverem recebido essa política por usuário não terão seus contatos migrados para o repositório unificado de contatos. Isso ocorre porque esses usuários estão sendo gerenciados pela política global, e o uso do repositório de contatos unificado foi desabilitado na política global.
  
Você pode verificar se os contatos de um usuário foram migrados com êxito para o repositório de contatos unificado executando o cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) de dentro do Shell de gerenciamento do Skype for Business Server:
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Se Test-CsUnifiedContactStore tiver êxito, isso significará que os contatos do usuário SIP:<span></span>kenmyer@<span></span>litwareinc. com foram migrados para o repositório de contatos unificado.
  
## <a name="rolling-back-the-unified-contact-store"></a>Revertendo o repositório unificado de contatos

Se você precisar remover os contatos de um usuário do repositório de contatos unificado (por exemplo, se o usuário precisar ser rehomeado no Microsoft Lync Server 2010 e, portanto, não puder mais usar o repositório de contatos unificado), você deverá fazer duas coisas. Primeiro, você deve atribuir ao usuário uma nova política de serviços de usuário, que proíba para armazenar contatos no repositório de contatos unificado. (Ou seja, uma política em que a propriedade UcsAllowed foi definida como $False.) Se você não tiver essa política, poderá criar uma usando um comando semelhante a isto:
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Em seguida, você pode atribuir essa nova política por usuário (NoUnifiedContactStore) usando um comando como o seguinte:
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

O comando anterior atribui a nova política ao usuário Ken Myer e também impede que os contatos de Ken sejam migrados para o repositório unificado de contatos.
  
> [!NOTE]
> Em alguns casos, é possível obter o mesmo efeito simplesmente cancelando a atribuição da política de serviços de usuário atual do usuário. Por exemplo, suponha que Ken Myer tenha uma política de serviços de usuário por usuário que habilita o repositório unificado de contatos, mas sua política global proíbe o uso do repositório unificado de contatos. Nesse caso, você pode cancelar a atribuição da política de serviços por usuário de Ken. Quando você fizer isso, Ken será automaticamente gerenciado pela política global e deixará de ter acesso ao repositório unificado de contatos. Para cancelar a atribuição de uma política por usuário previamente atribuída, use o mesmo comando exibido anteriormente, mas desta vez defina o parâmetro PolicyName como um valor nulo: Grant-CsUserServicesPolicy-Identity "Ken Myer"-PolicyName $Null 
  
É importante lembrar-se da frase "impede que os contatos de Ken sejam migrados para o repositório unificado de contatos" ao trabalhar com o repositório unificado de contatos. Simplesmente atribuir uma nova política de serviços de usuário a Ken não removerá seus contatos do repositório unificado de contatos. Quando um usuário faz logon no Skype for Business Server, o sistema verifica a política de serviços de usuário do usuário para ver se seus contatos devem ser mantidos no repositório de contatos unificado. Se a resposta for sim (ou seja, se a propriedade UcsAllowed estiver definida como $True), esses contatos serão migrados para o repositório unificado de contatos (pressupondo que eles ainda não estejam no repositório unificado de contatos). Se a resposta for não, o Skype for Business Server simplesmente ignorará os contatos do usuário e passará para a próxima tarefa. Isso significa que o Skype for Business Server não moverá automaticamente os contatos de um usuário do repositório de contatos unificado, independentemente do valor da propriedade UcsAllowed.
  
Isso também significa que, depois de atribuir o usuário a uma nova política de serviços de usuário, você deve executar o cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) para mover os contatos do usuário do Exchange Server e voltar para o Skype for Business Server. Por exemplo, após atribuir uma nova política de serviços de usuário a Ken Myer, você poderá remover seus contatos do repositório unificado de contatos usando o seguinte comando:
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Se você alterar a política de serviços de usuário, mas não executar o cmdlet Invoke-CsUcsRollback, os contatos de Ken não serão removidos do repositório unificado de contatos. E se você executar o Invoke-CsUcsRollback, mas não alterar a política de serviços de usuário de Ken Myer? Nesse caso, os contatos de Ken serão temporariamente removidos do repositório unificado de contatos. É importante atentar ao fato de que essa remoção é temporária. Depois que os contatos do Ken forem removidos do repositório de contatos unificado, o Skype for Business Server aguardará sete dias e verificará quais políticas de serviços de usuário foram atribuídas a Ken. Se uma política que permite o uso do repositório unificado de contatos ainda estiver atribuída a Ken, seus contatos serão automaticamente transferidos de volta para o repositório de contatos. Para remover permanentemente os contatos do repositório unificado de contatos, você precisa alterar a política de serviços de usuário e também executar o cmdlet Invoke-CsUcsRollback.
  
Devido ao grande número de variáveis que podem afetar a migração, é difícil estimar o tempo que será necessário para que todas as contas sejam totalmente migradas para o repositório unificado de contatos. No entanto, como regra geral, a migração não tem efeito imediato: até mesmo a migração de um pequeno número de contatos poderá demorar 10 minutos ou mais para ser concluída.
  

