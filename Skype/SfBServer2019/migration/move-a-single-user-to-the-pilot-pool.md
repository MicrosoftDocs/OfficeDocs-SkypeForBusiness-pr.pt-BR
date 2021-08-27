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
ms.localizationpriority: medium
description: Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server 2019 ou o Shell de Gerenciamento Skype for Business Server 2019. No exemplo abaixo, na coluna Pool do Registrador, pool01.contoso.net é o pool herdado e todos os seis desses usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server 2019 e o Shell de Gerenciamento Skype for Business Server 2019.
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596155"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um único usuário para o pool piloto

Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server 2019 ou o Shell de Gerenciamento Skype for Business Server 2019. No exemplo abaixo, na coluna Pool do **Registrador,** pool01.contoso.net **é** o pool herdado e todos os seis desses usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool Skype for Business Server 2019 usando o Painel de Controle Skype for Business Server 2019 e o Shell de Gerenciamento Skype for Business Server 2019. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Para mover um usuário usando o painel de controle Skype for Business Server 2019
  
1. Faça o logon no Servidor Front-End com uma conta que seja membro do grupo RTCUniversalServerAdmins ou que tenha a função administrativa CsAdministrator ou CsUserAdministrator.
    
2. Abra **Skype for Business Server Painel de Controle**.
    
3. Clique **em Usuários,** em **Pesquisar** e em **Encontrar**.
    
4. Selecione um usuário que você deseja mover para o pool Skype for Business Server 2019. Neste exemplo, vamos mover Sara Davis.
    
5. No menu **Ação**, selecione **Mover usuários selecionados para o pool**.
    
6. Na lista lista listada, selecione o pool Skype for Business Server 2019.
    
7. Clique em **Ação** e em **Mover usuários selecionados para o pool**. Clique em **OK**.
  
8. Verifique se a **coluna pool do Registrador** para o usuário agora contém o pool Skype for Business Server 2019, o que indica que o usuário foi movido com êxito. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Para mover um usuário usando o Shell de Gerenciamento Skype for Business Server 2019

1. Abra o Shell Skype for Business Server Gerenciamento.
    
2. Na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Em seguida, na linha de comando, digite o seguinte: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. A **identidade RegistrarPool** agora aponta para o pool Skype for Business Server 2019. A presença dessa identidade confirma que o usuário foi movido com sucesso. 

    > [!NOTE]
    > Para obter detalhes sobre o cmdlet **Get-CsUser,** execute: **Get-Help Get-CsUser -Detailed**
  

