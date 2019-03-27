---
title: Mover um usuário único ao pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover um usuário de seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell. No exemplo abaixo, na coluna pool registrador, pool01. contoso.NET é o pool herdado e seis desses usuários conectados a esse pool. Use os procedimentos a seguir para mover um usuário para sua Skype para pool de negócios Server 2019 usando Skype para painel de controle do Business Server 2019 e Skype do Shell de gerenciamento do servidor de negócios.
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880246"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um usuário único ao pool piloto

Você pode mover um usuário de seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell. No exemplo abaixo, na coluna **pool de registradores** , **pool01. contoso.NET** é o pool herdado e seis desses usuários conectados a esse pool. Use os procedimentos a seguir para mover um usuário para sua Skype para pool de negócios Server 2019 usando Skype para painel de controle do Business Server 2019 e Skype do Shell de gerenciamento do servidor de negócios. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover um usuário usando o Skype para o painel de controle do Business Server 2019
  
1. Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.
    
2. Abra o **Skype para painel de controle do servidor de negócios**.
    
3. Clique em **usuários**, clique em **Pesquisar**e clique em **Localizar**.
    
4. Selecione um usuário que você deseja mover para o Skype para Business Server 2019 pool. Neste exemplo, moveremos a usuária Sara Davis.
    
5. No menu **Ação**, selecione **Mover usuários selecionados para o pool**.
    
6. Na lista suspensa, selecione o Skype para Business Server 2019 pool.
    
7. Clique em **ação**e, em seguida, clique em **mover usuários selecionados para o pool**. Clique em **OK**.
  
8. Verifique se a coluna **pool de registrador** para o usuário agora contém o Skype para Business Server 2019 pool, que indica que o usuário foi movido com êxito. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover um usuário usando o Skype para o Shell de gerenciamento do Business Server 2019

1. Abra o Skype do Shell de gerenciamento do servidor de negócios.
    
2. Na linha de comando, digite o seguinte: 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Em seguida, na linha de comando, digite o seguinte: 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. A identidade **RegistrarPool** agora aponta para o Skype para Business Server 2019 pool. A presença dessa identidade confirma que o usuário foi movido com êxito. 

    > [!NOTE]
    > Para obter detalhes sobre o cmdlet **Get-CsUser** , execute: **Get-Help Get-CsUser-detalhadas**
  

