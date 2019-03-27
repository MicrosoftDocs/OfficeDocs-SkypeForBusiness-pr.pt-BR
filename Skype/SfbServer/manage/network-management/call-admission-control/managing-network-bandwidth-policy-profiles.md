---
title: Gerenciando perfis de política de largura de banda de rede
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos neste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: d27e4df1b549afd3c176f8b54453c44bb97819f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878897"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gerenciar perfis de política de largura de banda no Skype for Business Server

Use os procedimentos neste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.

## <a name="view-network-bandwidth-policy-profile-information"></a>Exibir informações de perfil de política de largura de banda de rede

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades. Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda. Você pode definir as limitações de largura de banda gerais e as limitações de sessão. Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas. Cada perfil de política de largura de banda pode ser associado um ou mais sites de rede. Use os procedimentos a seguir para exibir um perfil de política de largura de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para exibir um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja exibir.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de perfil de política de largura de banda de rede usando os cmdlets do Windows PowerShell

Perfis de largura de banda de rede podem ser exibidos usando o Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para exibir informações de perfil de política de largura de banda de rede

  - Para exibir informações sobre todos os seus perfis de política de largura de banda rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Isso retornará informações parecidas com:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Criar ou modificar perfis de política de largura de banda

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades. Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda. Você pode definir as limitações de largura de banda gerais e as limitações de sessão. Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas. Cada perfil de política de largura de banda pode ser associado um ou mais sites de rede. Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para criar um novo perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda** , clique em **novo**.

5.  Em **Novo perfil de política de largura de banda**, digite um nome no campo **nome** . Esse nome deve ser exclusivo entre todos os perfis de política de largura de banda.

6.  No campo de **limite de áudio** , digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a se alocar para todas as conexões de áudio, expressadas em kbps.

7.  Insira um valor numérico no campo de **limite de sessão de áudio** . Esse valor é a quantidade máxima de largura de banda a se alocar para uma conexão de áudio individual, expressado em kbps. Este valor deve ser 40 ou superior.

8.  Insira um valor numérico no campo de **limite de vídeo** . Esse valor é a quantidade máxima de largura de banda a se alocar para todas as conexões de vídeos, expressadas em kbps.

9.  Insira um valor numérico no campo de **limite de sessão de vídeo** . Esse valor é a quantidade máxima de largura de banda a se alocar para uma conexão de vídeo individual, expressado em kbps. Este valor deve ser 100 ou superior.

10. (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.

11. Clique em **Confirmar**.

    > [!NOTE]  
    > Criando um novo perfil de política de largura de banda não impõe restrições de largura de banda automaticamente. Primeiro você deve associar o perfil da política um site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar perfil da política de largura de banda** , modifique os campos conforme necessário (para obter detalhes, consulte [criar um novo perfil de política de largura de banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Clique em **Confirmar**.

    > [!NOTE]  
    > Quando você modifica o perfil de política de largura de banda, serão atualizadas imediatamente as limitações de largura de banda de todos os sites de rede associados a esse perfil de política de largura de banda.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Excluir perfis de política de largura de banda de rede

Como parte do controle de admissão de chamadas (CAC), uma política de largura de banda é usada para definir as limitações de largura de banda para determinadas modalidades. Skype para Business Server, modalidades somente de áudio e vídeos podem ser atribuídas as limitações de largura de banda. Você pode definir as limitações de largura de banda gerais e as limitações de sessão. Você pode usar o Skype para painel de controle do Business Server para criar, modificar ou excluir um perfil de contêiner para essas diretivas. Use os procedimentos a seguir para excluir um perfis de política de largura de banda de rede. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para excluir um perfil de política de largura de banda

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e clique em **Política de largura de banda**.

4.  Na página **Política de largura de banda** , clique no perfil da política de largura de banda que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um perfil por vez. Para fazer isso, pressione CTRL e selecione vários perfis, mantendo pressionada a tecla CTRL. Ou, para selecionar todos os perfis, clique em **Selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **Excluir**.
   

    > [!WARNING]  
    > Você não pode excluir um perfil de política de largura de banda que está associado um site de rede. Você deve primeiro remover a associação com o site de rede antes de excluir o perfil. 


## <a name="see-also"></a>Consulte Também

[Gerenciando o controle de admissão de chamada para sites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile.](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

