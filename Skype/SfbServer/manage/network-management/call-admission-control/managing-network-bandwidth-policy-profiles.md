---
title: Gerenciando perfis de política de largura de banda de rede
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.
ms.openlocfilehash: a360bd05ac3ee9cbd4d5a8d8d6578389dfc3068c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388119"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Gerenciando perfis de política de largura de banda no Skype for Business Server

Use os procedimentos deste artigo para exibir, criar, modificar ou excluir perfis de política de largura de banda de rede.

## <a name="view-network-bandwidth-policy-profile-information"></a>Exibir informações de perfil de política de largura de banda de rede

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Skype for Business Server, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel Skype for Business Server controle para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para exibir um perfil de política de largura de banda. 

### <a name="to-view-a-bandwidth-policy-profile"></a>Para exibir um perfil de política de largura de banda

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede** e, em seguida, clique em **Política de largura de banda**.

4.  Na página **Política de Largura** de Banda, clique no perfil de política de largura de banda que você deseja exibir.

5.  No painel **Ações**, clique em **Mostrar detalhes**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de perfil de política de largura de banda de rede usando Windows PowerShell cmdlets

Os perfis de largura de banda de rede podem ser exibidos usando Windows PowerShell e o cmdlet Get-CsNetworkBandwidthPolicyProfile de rede. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>Para exibir informações de perfil de política de largura de banda de rede

  - Para exibir informações sobre todos os perfis de política de largura de banda de rede, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    Isto retorna informações semelhantes à seguinte:
    
    Identidade : RedmondBandwidthPolicy<br/>
    BWPolicy : {BWLimit=200; BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio, <br/>
                        BWLimit=1400; BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID : RedmondBandwidthPolicy<br/>
    Descrição :

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Criar ou modificar perfis de política de largura de banda

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Skype for Business Server, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel Skype for Business Server controle para criar, modificar ou excluir um perfil de contêiner para essas políticas. Cada perfil de política de largura de banda pode ser associado a um ou mais sites de rede. Use os procedimentos a seguir para criar ou modificar um perfil de política de largura de banda. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>Para criar um novo perfil de política de largura de banda

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em Política **de Largura de Banda**.

4.  Na página **Política de largura de banda**, clique em **Novo**.

5.  Em **Novo Perfil de Política de Largura de Banda**, digite um nome no campo **Nome**. Esse nome deve ser único entre todos os perfis de política de largura de banda.

6.  No campo **Limite de áudio**, digite um valor numérico. Esse valor é a quantidade máxima de largura de banda a ser alocada a todas as conexões de áudio, expressa em kbps.

7.  Insira um valor numérico no campo **Limite da sessão de áudio**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de áudio individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 40.

8.  Insira um valor numérico no campo **Limite de vídeo**. Esse valor é quantidade máxima de largura de banda a ser alocada para todas as conexões de vídeo, expressa em kbps.

9.  Insira um valor numérico no campo **Limite de sessão de vídeo**. Esse valor é a quantidade máxima de largura de banda a ser alocada para uma conexão de vídeo individual, expressa em kbps. Esse valor precisa ser igual a ou maior que 100.

10. (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre esse perfil da política de largura de banda que não pode ser expressa somente pelo nome.

11. Clique em **Confirmar**.

    > [!NOTE]  
    > Criar um novo perfil de política de largura de banda não reforça as restrições de largura de banda automaticamente. É preciso, primeiro, associar o perfil da política com um site. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar um perfil de política de largura de banda

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em Política **de Largura de Banda**.

4.  Na página **Política de largura de banda**, clique no perfil da política de largura de banda que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar Perfil da Política de Largura** de Banda, modifique os campos conforme necessário (para obter detalhes, consulte [Para criar um novo perfil de política de largura de banda](#to-create-a-new-bandwidth-policy-profile)).

7.  Clique em **Confirmar**.

    > [!NOTE]  
    > Ao modificar o perfil de política de largura de banda, as limitações de largura de banda de todos os sites da rede associados a esse perfil serão atualizadas imediatamente.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Excluir perfis de política de largura de banda de rede

Como parte de um controle de admissão de chamadas (CAC), uma diretiva de largura de banda é utilizada para definir limites para certas modalidades. No Skype for Business Server, somente as modalidades de áudio e vídeo podem ser atribuídas a limitações de largura de banda. Você pode configurar os limites gerais de banda e os limites de sessão. Você pode usar o painel Skype for Business Server controle para criar, modificar ou excluir um perfil de contêiner para essas políticas. Use os seguintes procedimentos para excluir um perfil de política de largura de banda de rede. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>Para excluir um perfil de política de largura de banda

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e clique em Política **de Largura de Banda**.

4.  Na página **Política de largura de banda**, clique no perfil de política de largura de banda que você deseja excluir.

    > [!NOTE]  
    > Você pode excluir mais de um perfil por vez. Para isso, pressione CTRL e selecione vários perfis mantendo a tecla CTRL pressionada. Ou, para selecionar perfis, clique em **Selecionar tudo** no menu **Editar**.

5.  No menu **Editar**, clique em **Excluir**.
   

    > [!WARNING]  
    > Você não pode excluir um perfil de política de largura de banda que esteja associado a um site da rede. É preciso primeiro remover a associação com o site antes de poder excluir o perfil. 


## <a name="see-also"></a>Confira Também

[Gerenciando o controle de admissão de chamada para sites](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
