---
title: 'Implantar o armazenamento unificado de contatos Skype for Business Server '
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumo: Habilita o armazenamento unificado de contatos Skype for Business Server.'
ms.openlocfilehash: 459626fe40f76cc19534aaff67d1b1b39c268469
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748827"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implantar o armazenamento unificado de contatos Skype for Business Server
 
**Resumo:** Habilita o armazenamento unificado de contatos Skype for Business Server.
  
Habilenciar o armazenamento unificado de contatos Skype for Business Server não requer configurações de topologia. Para habilitar o armazenamento unificado de contatos para usuários:
  
- Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).
    
- Os usuários se conectarão Skype for Business pelo menos uma vez.
    
Depois que os contatos de um usuário são migrados, o que acontece automaticamente quando um usuário faz logor com o Skype for Business, o usuário pode acessar e gerenciar seus contatos do Skype for Business do Skype for Business, Outlook 2013 ou Outlook Web Access. O usuário não precisa estar conectado Skype for Business gerenciar seus contatos do Outlook ou Outlook Web Access.
  
> [!IMPORTANT]
> Se um usuário entrar no Skype for Business após a migração, os contatos e grupos estarão disponíveis e atualizados, mas o usuário não poderá gerenciar (ou seja, adicionar, excluir, mover, marcar, desatar ou modificar) esses contatos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuários para o armazenamento unificado de contatos

Quando você implanta Skype for Business Server e publica a topologia, o armazenamento unificado de contatos é habilitado para todos os usuários por padrão. Você não precisa tomar nenhuma ação adicional para habilitar o armazenamento unificado de contatos depois de implantar Skype for Business Server. Contudo, você pode usar o **Set-CsUserServicesPolicy** cmdlet para definir quais usuários têm o armazenamento unificado de contatos disponível. Você pode habilitar esse recurso globalmente, por local, por tenant ou por indivíduos ou grupos de indivíduos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para permitir o armazenamento unificado de contatos

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **e** clique Skype for Business Server Shell **de Gerenciamento.**
    
2. Faça um dos seguintes:
    
   - Para habilitar o armazenamento de contatos unificado globalmente para todos os Skype for Business Server usuários, entre o seguinte cmdlet na interface Windows PowerShell linha de comando:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Para habilitar o armazenamento unificado de contatos para os usuários em um site específico, no prompt, digite:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Para habilitar o armazenamento unificado de contatos por locatário, no prompt, digite:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Para habilitar o armazenamento unificado de contatos para usuários específicos, no prompt, digite:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário. 
  
    Por exemplo:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > No exemplo anterior, o primeiro comando criar uma nova política de acordo com o usuário chamada Usuários do UCS Permitidos, com o sinalizador AcsAllowed definido para True. O segundo comando define a política ao usuário com nome de Ken Myer, o que significa que Ken Myer está autorizado a ter armazenamento unificado de contatos.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuários para o armazenamento unificado de contatos

Os contatos de um usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:
  
- For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.
    
- Foi provisionado com uma caixa de correio Exchange 2013 e entrou na caixa de correio pelo menos uma vez.
    
- Entre usando um cliente Skype for Business rich.
    
Se o usuário entrar com um Lync ou cliente anterior ou se o usuário não estiver conectado a um servidor do Exchange 2013, a política de serviços de usuário será ignorada e os contatos do usuário permanecerão em Skype for Business Server.
  
É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos: 
  
- Verifique a chave do registro no computador cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ URL SIP \> \UCS
    
    Se os contatos do usuário são armazenados no Exchange 2013, essa chave contém um valor inUCSMode com um valor de 2165.
    
- Execute o cmdlet **Test-CsUnifiedContactStore**. Na linha de comando Skype for Business Server Shell de Gerenciamento, digite:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.
    
## <a name="roll-back-migrated-users"></a>Reverter usuários migrados

Se você precisar reverter o recurso de armazenamento unificado de contatos, reverter os contatos somente se você mover o usuário de volta para o Exchange 2010 ou Lync Server 2010. Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**. Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada. Por exemplo, se um usuário for reacionado porque o Exchange 2013 é reacionado para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do armazenamento de contatos unificado será iniciada novamente sete dias após a reação, desde que o armazenamento unificado de contatos ainda esteja habilitado para o usuário na política de serviços de usuário.
  
O cmdlet **Move-CsUser** rola automaticamente o armazenamento de contatos do usuário de Exchange 2013 para Skype for Business Server nas seguintes situações:
  
- Quando os usuários são movidos do Skype for Business Server para o Microsoft Lync Server 2013 ou o Lync Server 2010. 
    
- Quando os usuários são migrados entre locais, como quando um usuário é movido do Skype for Business Online para o Skype for Business Server local ou vice-versa.
    
Importar os dados do repositório de contato unificado de um banco de dados de backup pode causar com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:
  
- Se você exportar listas de contatos antes que os contatos dos usuários sejam migrados para o Exchange 2013 e, depois da migração, importar os mesmos dados, os dados do armazenamento unificado de dados e listas de contatos serão corrompidos.
    
- Se você exportar dados do usuário depois de migrar usuários para o Exchange 2013, reverter a migração e, por algum motivo, importar os dados após a migração, os dados de armazenamento unificado e listas de contatos serão corrompidos.
    
> [!IMPORTANT]
> Antes de mover uma caixa de correio Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve certificar-se de que o administrador do Skype for Business Server tenha rolado o Skype for Business Server contatos do usuário de Exchange 2013 para Skype for Business Server. Para reverter os contatos unificados do armazenamento de contatos para Skype for Business Server, consulte o procedimento "Para reverter contatos unificados do armazenamento de contatos do Exchange 2013 para Skype for Business Server", mais adiante nesta seção. 
  
 **Como reverter contatos do usuário:** Se você usar o cmdlet **Move-CsUser** para mover usuários entre o Skype for Business Server 2015 e o Lync Server 2010, poderá ignorar essas etapas porque o cmdlet **Move-CsUser** reajusta automaticamente o armazenamento unificado de contatos quando ele move os usuários do Skype for Business Server 2015 para o Lync Server 2010. **O Move-CsUser** não desabilita a política de armazenamento unificado de contatos, portanto, a migração para o armazenamento unificado de contatos será recorrência se o usuário for movido de volta para o Skype for Business Server 2015.
  

