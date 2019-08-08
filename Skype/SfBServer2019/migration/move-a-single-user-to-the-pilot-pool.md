---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019. No exemplo a seguir, na coluna pool de registradores, pool01.contoso.net é o pool herdado e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server.
ms.openlocfilehash: 456035cfd917f620383d4dff70f6366cd73d530e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237762"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um único usuário para o pool piloto

Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019. No exemplo a seguir, na coluna **pool** de registradores, **pool01.contoso.net** é o pool herdado e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover um usuário usando o painel de controle do Skype for Business Server 2019
  
1. Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.
    
2. Abra o **painel de controle do Skype for Business Server**.
    
3. Clique em **usuários**, clique em **Pesquisar**e, em seguida, clique em **Localizar**.
    
4. Selecione o usuário que você deseja mover para o pool do Skype for Business Server 2019. Neste exemplo, moveremos a usuária Sara Davis.
    
5. No menu **Ação**, selecione **Mover usuários selecionados para o pool**.
    
6. Na lista suspensa, selecione o pool do Skype for Business Server 2019.
    
7. Clique em **ação**e, em seguida, clique em **mover os usuários selecionados para o pool**. Clique em **OK**.
  
8. Verifique se a coluna do **pool** de registradores do usuário agora contém o pool do Skype for Business Server 2019, que indica que o usuário foi movido com êxito. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover um usuário usando o Shell de gerenciamento do Skype for Business Server 2019

1. Abra o Shell de gerenciamento do Skype for Business Server.
    
2. Na linha de comando, digite o seguinte: 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Em seguida, na linha de comando, digite o seguinte: 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. A identidade **RegistrarPool** agora aponta para o pool do Skype for Business Server 2019. A presença dessa identidade confirma que o usuário foi movido com êxito. 

    > [!NOTE]
    > Para obter detalhes sobre o cmdlet **Get-CsUser** , execute: **Get-Help Get-CsUser-detailed**
  

