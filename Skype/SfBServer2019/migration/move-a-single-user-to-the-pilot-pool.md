---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019. No exemplo abaixo, na coluna pool de registrador, pool01.contoso.net é o pool herdado e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752503"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um único usuário para o pool piloto

Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019. No exemplo abaixo, na coluna **pool de registrador** , **pool01.contoso.net** é o pool herdado e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover um usuário usando o painel de controle do Skype for Business Server 2019
  
1. Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.
    
2. Abra o **painel de controle do Skype for Business Server**.
    
3. Clique em **usuários**, em **Pesquisar**e em **Localizar**.
    
4. Selecione um usuário que você deseja mover para o pool do Skype for Business Server 2019. Neste exemplo, vamos mover Sara Davis.
    
5. No menu **Ação**, selecione **Mover usuários selecionados para o pool**.
    
6. Na lista suspensa, selecione o pool do Skype for Business Server 2019.
    
7. Clique em **Ação** e em **Mover usuários selecionados para o pool**. Clique em **OK**.
  
8. Verifique se a coluna **pool do registrador** para o usuário agora contém o pool do Skype for Business Server 2019, que indica que o usuário foi movido com êxito. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover um usuário usando o Shell de gerenciamento do Skype for Business Server 2019

1. Abra o Shell de gerenciamento do Skype for Business Server.
    
2. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Em seguida, na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Agora, a identidade **RegistrarPool** aponta para o pool do Skype for Business Server 2019. A presença dessa identidade confirma que o usuário foi movido com sucesso. 

    > [!NOTE]
    > Para obter detalhes sobre o cmdlet **Get-CsUser** , execute: **Get-Help Get-CsUser-detailed**
  

