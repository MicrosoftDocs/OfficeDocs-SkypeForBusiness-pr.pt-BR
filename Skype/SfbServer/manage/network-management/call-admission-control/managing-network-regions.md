---
title: Gerenciando regiões de rede
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
description: Região de rede * são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817480"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gerenciar regiões de rede no Skype for Business Server

*Regiões de rede* são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia. Use os procedimentos a seguir para exibir, criar ou modificar regiões de rede. Por exemplo, se você já tiver criado regiões de rede para um recurso de voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede. No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central. 

Use os procedimentos deste artigo para exibir informações de região de rede ou criar, modificar ou excluir regiões de rede. 

## <a name="view-network-region-information"></a>Exibir informações de região de rede 


Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Todas as regiões de rede devem estar associadas a um site central. O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução. Você pode usar o painel de controle do Skype for Business Server para exibir regiões de rede. As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo. Use este tópico para exibir regiões de rede existentes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para ver informações sobre uma região de rede com o painel de controle do Skype for Business Server

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja exibir.
  
    > [!NOTE]  
    > Você só pode exibir uma região de cada vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de região de rede usando cmdlets do Windows PowerShell

Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para ver as informações da região de rede

  - Para ver as informações sobre todas as suas regiões de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkRegion
    
    Isso retornará informações parecidas com:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Criar ou modificar regiões de rede 

Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Todas as regiões de rede devem estar associadas a um site central. O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução. Você pode usar o painel de controle do Skype for Business Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para criar e modificar regiões de rede. 

### <a name="to-create-a-network-region"></a>Para criar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique em **novo**.

5.  Na página **nova região** , digite um valor no campo **nome** . Esse valor deve ser exclusivo na implantação do Skype for Business Server.

6.  Na lista suspensa **site central** , selecione o site central para esta região de rede.

7.  A caixa de seleção **habilitar caminho alternativo de áudio** está marcada por padrão. Esse campo determina se as chamadas de áudio serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal. Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet. Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.

8.  A caixa de seleção **habilitar caminho alternativo de vídeo** está marcada por padrão. Esse campo determina se as chamadas com vídeo serão roteadas por meio de um caminho alternativo se a largura de banda adequada não existir no caminho principal. Desmarque essa caixa de seleção apenas se precisar desativar o Offload para a Internet. Se qualquer uma de suas chamadas for chamada pela Internet, essa caixa de seleção deve ser marcada, independentemente das configurações de largura de banda.

9.  Adicionais Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa apenas pelo nome.

10. Clique em **Confirmar**.

A tabela de **sites associados** não é usada para criar uma região de rede. Você associa um site com uma região quando cria ou modifica o site. Para obter detalhes, consulte [Gerenciando o controle de admissão de chamadas para sites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Para modificar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar caminhos alternativos de áudio e vídeo e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente neste tópico.

7.  Clique em **Confirmar**.

Não é possível modificar os **sites associados** nesta página. A lista de sites associados é fornecida para referência para que você saiba quais sites serão afetados quando você modificar as configurações de região.


## <a name="delete-existing-network-regions"></a>Excluir regiões de rede existentes 

Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Todas as regiões de rede devem estar associadas a um site central. O site central é o site do Data Center no qual o serviço de política de largura de banda do controle de admissão de chamadas (CAC) está em execução. Você pode usar o painel de controle do Skype for Business Server para configurar regiões de rede. As regiões de rede incluem configurações que determinam se caminhos alternativos pela Internet são permitidos para conexões de áudio e vídeo. No painel de controle do Skype for Business Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para excluir regiões de rede existentes. 

### <a name="to-delete-a-network-region"></a>Para excluir uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja excluir.
  
    > [!NOTE]  
    > Você pode excluir mais de uma região de cada vez. Para fazer isso, pressione CTRL e selecione várias regiões enquanto mantém a tecla CTRL pressionada. Ou, para selecionar todas as regiões, clique em **selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **excluir**.

6.  Clique em **OK**.


    > [!WARNING]  
    > Uma região de rede não poderá ser removida se estiver associada a um site de rede. Se você tentar remover uma região associada a um site, uma mensagem de erro será exibida. Para ver se uma região está associada a qualquer site, selecione a região e clique em **Mostrar detalhes** no menu **Editar** .


## <a name="see-also"></a>Confira também

[Gerenciando rotas de região de rede](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
