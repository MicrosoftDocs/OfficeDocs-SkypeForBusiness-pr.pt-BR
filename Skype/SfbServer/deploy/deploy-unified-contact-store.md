---
title: 'Implantar o armazenamento unificado de contatos no Skype para Business Server '
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumo: Habilite o repositório unificado de contatos no Skype para Business Server.'
ms.openlocfilehash: 5e7fb34d03459be5066d154e89fa8e27dc060757
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882562"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Implantar o armazenamento unificado de contatos no Skype para Business Server
 
**Resumo:** Habilite o repositório unificado de contatos no Skype para Business Server.
  
Habilitar o repositório unificado de contatos no Skype para Business Server não exige qualquer configuração de topologia. Para habilitar o repositório unificado de contatos para os usuários é necessário:
  
- Que a política do repositório unificado de contatos esteja habilitada (ela é habilitada por padrão).
    
- Os usuários fazer logon com Skype para negócios pelo menos uma vez.
    
Depois que contatos um usuário foram migrados, que ocorre automaticamente quando um usuário fizer com Skype para os negócios, o usuário pode acessar e gerenciar seu Skype para contatos comerciais do Skype para negócios, Outlook 2013 ou Outlook Web Access. O usuário não precisa estar conectado ao Skype for Business gerenciar seus contatos do Outlook ou o Outlook Web Access.
  
> [!IMPORTANT]
> Se um usuário fizer logon de Skype para negócios após a migração, contatos e grupos disponíveis e atualizadas, mas o usuário não pode gerenciar (isto é, adicionar, excluir, mover, marca, quando você formatação ou modificar) esses contatos. 
  
## <a name="enable-users-for-unified-contact-store"></a>Habilitar usuários para repositório unificado de contatos

Quando você implantar Skype para Business Server e publica a topologia, o armazenamento unificado de contatos está habilitado para todos os usuários por padrão. Você não precisará executar qualquer ação adicional para permitir o armazenamento de contato unificado após a implantação do Skype para Business Server. Contudo, você pode usar o cmdlet **Set-CsUserServicesPolicy** para definir quais usuários têm o repositório unificado de contatos disponível. Você pode habilitar esse recurso globalmente, por local, por locatário ou por indivíduos ou grupos de indivíduos.
  
### <a name="to-enable-users-for-unified-contact-store"></a>Para permitir o repositório unificado de contatos

1. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
2. Execute qualquer uma das seguintes ações:
    
   - Para habilitar o armazenamento unificado de contatos globalmente para todos os Skype para usuários corporativos Server, inter o seguinte cmdlet na interface de linha de comando do Windows PowerShell:
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos para os usuários em um local específico, digite no prompt:
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos por locatário, digite no prompt:
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Por exemplo:
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Para permitir o repositório unificado de contatos para usuários específicos, digite no prompt:
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Você também pode alterar o URI do SIP ou o usuário remoto em vez do nome do usuário. 
  
    Por exemplo:
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > No exemplo anterior, o primeiro comando cria uma nova política por usuário chamada Usuários do UCS Permitidos, com o sinalizador AcsAllowed definido como True. O segundo comando atribui a política ao usuário com o nome Ken Myer, o que significa que Ken Myer está habilitado para o repositório unificado de contatos.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrar usuários para o repositório unificado de contatos

Contatos do usuário são migrados automaticamente para o servidor Exchange 2013 quando o usuário:
  
- For atribuído com uma política de serviços do usuário com UcsAllowed definido para True.
    
- Tenha sido provisionado com uma caixa de correio do Exchange 2013 e tiver entrado na caixa de correio pelo menos uma vez.
    
- Faça o login usando um Skype para clientes avançados de negócios.
    
Se o usuário fizer logon com um cliente anterior ou o Lync, ou se o usuário não estiver conectado a um servidor Exchange 2013, a política de serviços do usuário será ignorada e os contatos do usuário permanecem no Skype para Business Server.
  
É possível determinar se os contatos do usuário foram migrados usando um dos seguintes métodos: 
  
- Verifique a chave do registro no computador cliente:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    Se os contatos do usuário são armazenados no Exchange 2013, essa chave contém um valor do InUCSMode de 2165.
    
- Execute o cmdlet **Test-CsUnifiedContactStore**. No Skype para a linha de comando do Shell de gerenciamento do servidor de negócios, digite:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Se o **Test-CsUnifiedContactStore** tiver êxito, os contatos do usuário foram migrados para o repositório de contatos unificados.
    
## <a name="roll-back-migrated-users"></a>Reversão de Usuários Migrados

Se você precisar reverter o contato unificado armazenar recurso, reverter os contatos somente se você mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010. Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**. Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada. Por exemplo, se um usuário é revertido porque Exchange 2013 será revertida para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório unificado de contatos será iniciada novamente sete dias após a reversão, desde que o repositório de contato unificado ainda está habilitado para o usuário na política de serviços de usuário.
  
O cmdlet **Move-CsUser** automaticamente reverte o repositório de contatos do usuário do Exchange 2013 para Skype para Business Server nas seguintes situações:
  
- Quando os usuários são movidos do Skype para Business Server para Microsoft Lync Server 2013 ou o Lync Server 2010. 
    
- Quando os usuários são migrados entre locais, como quando um usuário é movido do Skype para Business Online para Skype para Business Server local, ou vice-versa.
    
Importar os dados do repositório de contato unificado de um banco de dados de backup pode fazer com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo:
  
- Se você exportar listas de contato antes de contatos dos usuários são migrados para o Exchange 2013 e em seguida, após a migração, importe os mesmos dados, os dados do repositório unificado de contatos e as listas de contatos serão corrompidas.
    
- Se você exportar os dados do usuário depois de migrar os usuários para o Exchange 2013, reverter a migração e, em seguida, por algum motivo você importar os dados de após a migração, o contato unificado armazenar dados e listas de contatos serão corrompidas.
    
> [!IMPORTANT]
> Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve Certifique-se de que o Skype para o administrador do servidor de negócios tem primeiro revertida o Skype para contatos do usuário de servidor de negócios do Exchange 2013 para Skype para Servidor de negócios. Para reverter os contatos de repositório unificado de contatos para Skype para Business Server, consulte o procedimento "para reverter os contatos de repositório unificado de contatos do Exchange 2013 para Skype para Business Server," mais adiante nesta seção. 
  
 **Como reverter contatos do usuário:** Se você usar o cmdlet **Move-CsUser** para mover usuários entre Skype para Business Server 2015 e o Lync Server 2010, pule essas etapas porque o cmdlet **Move-CsUser** automaticamente reverte repositório unificado de contatos quando ele se move os usuários do Skype para 2015 comerciais de servidor para o Lync Server 2010. **Move-CsUser** não desabilite a política do repositório unificado de contatos, para que a migração para o armazenamento unificado de contatos será executado se o usuário é movido para Skype para Business Server 2015.
  

