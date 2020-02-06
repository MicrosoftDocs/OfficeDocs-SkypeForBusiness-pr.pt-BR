---
title: Gerenciando perfis de política de largura de banda de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817500"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gerenciar perfis de política de largura de banda no Skype for Business Server

Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.

## <a name="view-network-bandwidth-policy-profile-information"></a>Exibir informações do perfil da política de largura de banda de rede

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades. No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas. Você pode definir limitações gerais de largura de banda e limitações de sessão. Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para exibir um perfil de política de largura de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para exibir um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede** e, em seguida, em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja exibir.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações do perfil da política de largura de banda de rede usando cmdlets do Windows PowerShell

Os perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para ver as informações do perfil da política de largura de banda de rede

  - Para ver informações sobre todos os perfis da política de largura de banda de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Isso retornará informações parecidas com:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Criar ou modificar perfis de política de largura de banda

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades. No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas. Você pode definir limitações gerais de largura de banda e limitações de sessão. Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para criar um novo perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique em **novo**.

5.  Em **novo perfil de política de largura de banda**, digite um nome no campo **nome** . Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.

6.  No campo **limite de áudio** , digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de áudio, expressa em Kbps.

7.  Insira um valor numérico no campo **limite da sessão de áudio** . Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em Kbps. Esse valor deve ser 40 ou superior.

8.  Insira um valor numérico no campo **limite de vídeo** . Esse valor é a quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em Kbps.

9.  Insira um valor numérico no campo **limite da sessão de vídeo** . Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em Kbps. Esse valor deve ser 100 ou superior.

10. Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil de política de largura de banda que não pode ser expresso apenas com o nome.

11. Clique em **Confirmar**.

    > [!NOTE]  
    > A criação de um novo perfil de política de largura de banda não impõe automaticamente restrições de largura de banda. Você deve primeiro associar o perfil de política a um site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte [criar um novo perfil de política de largura de banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Clique em **Confirmar**.

    > [!NOTE]  
    > Quando você modifica o perfil da política de largura de banda, ele atualiza imediatamente as limitações de largura de banda de todos os sites de rede associados a este perfil de política de largura de banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Excluir perfis de política de largura de banda de rede

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir limitações de largura de banda para determinadas modalidades. No Skype for Business Server, apenas as modalidades de áudio e de vídeo podem ter limitações de largura de banda atribuídas. Você pode definir limitações gerais de largura de banda e limitações de sessão. Você pode usar o painel de controle do Skype for Business Server para criar, modificar ou excluir um perfil de contêiner para essas políticas. Use os procedimentos a seguir para excluir um perfil de política de largura de banda de rede. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para excluir um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em política de **largura de banda**.

4.  Na página **política de largura de banda** , clique no perfil de política de largura de banda que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um perfil de cada vez. Para fazer isso, pressione CTRL e selecione vários perfis enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todos os perfis, clique em **selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **excluir**.
   

    > [!WARNING]  
    > Não é possível excluir um perfil de política de largura de banda associado a um site de rede. Você deve primeiro remover a associação com o site de rede antes de poder excluir o perfil. 


## <a name="see-also"></a>Confira também

[Gerenciando o controle de admissão de chamadas para sites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

