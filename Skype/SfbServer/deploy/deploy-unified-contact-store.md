---
title: 'Implantar repositório de contatos unificado no Skype for Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumo: habilite o repositório de contatos unificado no Skype for Business Server.'
ms.openlocfilehash: 382b4ed059c4066ae862bb3fe24b98b4bdde2a18
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798088"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implantar repositório de contatos unificado no Skype for Business Server
 
**Resumo:** Habilite o repositório de contatos unificado no Skype for Business Server.
  
Habilitar o repositório de contatos unificado no Skype for Business Server não requer nenhuma configuração de topologia. Para habilitar o repositório unificado de contatos para os usuários é necessário:
  
- Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).
    
- Os usuários fazem logon com o Skype for Business pelo menos uma vez.
    
Após a migração dos contatos de um usuário, o que acontece automaticamente quando um usuário faz logon com o Skype for Business, o usuário pode acessar e gerenciar seus contatos do Skype for Business pelo Skype for Business, Outlook 2013 ou Outlook Web Access. O usuário não precisa estar conectado ao Skype for Business para gerenciar seus contatos do Outlook ou do Outlook Web Access.
  
> [!IMPORTANT]
> Se um usuário fizer logon pelo Skype for Business após a migração, os contatos e grupos estarão disponíveis e atualizados, mas o usuário não poderá gerenciar (ou seja, adicionar, excluir, mover, marcar, remover ou modificar) esses contatos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuários para repositório unificado de contatos

Quando você implanta o Skype for Business Server e publica a topologia, o repositório de contatos unificado é habilitado para todos os usuários por padrão. Você não precisa executar nenhuma ação adicional para habilitar o repositório de contatos unificado após a implantação do Skype for Business Server. Contudo, você pode usar o cmdlet **Set-CsUserServicesPolicy** para definir quais usuários têm o repositório unificado de contatos disponível. Você pode habilitar esse recurso globalmente, por local, por locatário ou por indivíduos ou grupos de indivíduos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para permitir o repositório unificado de contatos

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
2. Execute qualquer uma das seguintes ações:
    
   - Para habilitar o repositório de contatos unificado globalmente para todos os usuários do Skype for Business Server, entre o cmdlet a seguir na interface de linha de comando do Windows PowerShell:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos para os usuários em um local específico, digite no prompt:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos por locatário, digite no prompt:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos para usuários específicos, digite no prompt:
    
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
    > No exemplo anterior, o primeiro comando cria uma nova política por usuário chamada Usuários do UCS Permitidos, com o sinalizador AcsAllowed definido como True. O segundo comando atribui a política ao usuário com o nome Ken Myer, o que significa que Ken Myer está habilitado para o repositório unificado de contatos.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuários para o repositório unificado de contatos

Os contatos de um usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:
  
- For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.
    
- Foi provisionado com uma caixa de correio do Exchange 2013 e entrou na caixa de correio pelo menos uma vez.
    
- Conecta-se usando um cliente avançado Skype for Business.
    
Se o usuário fizer logon com um cliente do Lync ou anterior, ou se o usuário não estiver conectado a um servidor do Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecerão no Skype for Business Server.
  
É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos: 
  
- Verifique a chave do registro no computador cliente:
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<URL\>SIP \UCS
    
    Se os contatos do usuário estiverem armazenados no Exchange 2013, essa chave contém um valor de InUCSMode com um valor de 2165.
    
- Execute o cmdlet **Test-CsUnifiedContactStore**. Na linha de comando do Shell de gerenciamento do Skype for Business Server, digite:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.
    
## <a name="roll-back-migrated-users"></a>Reversão de Usuários Migrados

Se você precisar reverter o recurso de repositório de contatos unificado, reverta os contatos apenas se mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010. Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**. Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada. Por exemplo, se um usuário for revertido porque o Exchange 2013 é revertido para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório de contatos unificado será iniciada novamente sete dias após a reversão, desde que o repositório de contatos unificado ainda está habilitado para o usuário na política de serviços de usuário.
  
O cmdlet **move-CsUser** retorna automaticamente a loja de contatos do usuário do Exchange 2013 para o Skype for Business Server nas seguintes situações:
  
- Quando os usuários forem movidos do Skype for Business Server para o Microsoft Lync Server 2013 ou o Lync Server 2010. 
    
- Quando os usuários são migrados de forma cruzada, como quando um usuário é movido do Skype for Business online para o Skype for Business Server no local, ou vice-versa.
    
Importar os dados do repositório de contato unificado de um banco de dados de backup pode fazer com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:
  
- Se você exportar listas de contatos antes de os contatos dos usuários serem migrados para o Exchange 2013 e depois, após a migração, importar os mesmos dados, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.
    
- Se você exportar dados do usuário depois de migrar os usuários para o Exchange 2013, reverta a migração e, por algum motivo, importar os dados após a migração, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.
    
> [!IMPORTANT]
> Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve verificar se o administrador do Skype for Business Server primeiro reverteu os contatos do usuário do Skype for Business Server do Exchange 2013 para o Skype for Business Server. Para reverter contatos do repositório de contatos unificados para o Skype for Business Server, consulte procedimento "para reverter contatos do repositório de contatos unificados do Exchange 2013 para o Skype for Business Server", posteriormente nesta seção. 
  
 **Como recuperar contatos do usuário:** Se você usar o cmdlet **move-CsUser** para mover os usuários entre o Skype for Business Server 2015 e o Lync Server 2010, poderá ignorar essas etapas porque o cmdlet **move-CsUser** automaticamente recupera o repositório de contatos unificado quando move usuários do Skype for Business Server 2015 para o Lync Server 2010. **Move-CsUser** não desabilita a política de repositório de contatos unificado, portanto, a migração para o repositório de contatos unificado será recorrente se o usuário for movido de volta para o Skype for Business Server 2015.
  

