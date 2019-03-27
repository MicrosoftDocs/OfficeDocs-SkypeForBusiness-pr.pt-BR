---
title: Gerenciando as regiões de rede
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Região de rede * são os hubs de rede ou o backbones usados na configuração do bypass de mídia, E9-1-1 e controle de admissão chamada.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877626"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gerenciar regiões de rede no Skype for Business Server

*Regiões de rede* são os hubs de rede ou o backbones usados na configuração do bypass de mídia, E9-1-1 e controle de admissão chamada. Use os procedimentos a seguir para exibir, criar ou modificar regiões de rede. Por exemplo, se você já criou regiões de rede para um recurso de voz, você não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usará esses mesmos regiões de rede. No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central. 

Use os procedimentos neste artigo para exibir informações de região de rede ou criar, modificar ou excluir as regiões de rede. 

## <a name="view-network-region-information"></a>Exibir informações de região de rede 


Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas. Cada região de rede deve ser associado um site central. O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado. Você pode usar o Skype para painel de controle do Business Server para exibir as regiões de rede. Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo. Use este tópico para exibir as regiões de rede existente. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Para exibir informações sobre uma região de rede com Skype para painel de controle do servidor de negócios

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja exibir.
  
    > [!NOTE]  
    > Você pode exibir apenas uma região por vez.

5.  No menu **Editar**, clique em **Exibir detalhes**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualizando informações de região de rede usando os cmdlets do Windows PowerShell

Você pode exibir informações de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegion** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Para exibir informações de região de rede

  - Para exibir informações sobre todas as regiões de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkRegion
    
    Isso retornará informações parecidas com:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Criar ou modificar regiões de rede 

Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas. Cada região de rede deve ser associado um site central. O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado. Você pode usar o Skype para painel de controle do Business Server para configurar regiões de rede. Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para criar e modificar regiões de rede. 

### <a name="to-create-a-network-region"></a>Para criar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique em **novo**.

5.  Na página **Nova região** , digite um valor no campo **nome** . Este valor deve ser exclusivo dentro de sua Skype para implantação de servidor de negócios.

6.  Na lista suspensa **site Central** , selecione o site central para essa região de rede.

7.  A caixa de seleção **Habilitar áudio caminho alternativo** está marcada por padrão. Esse campo determina se chamadas de áudio serão roteadas por um caminho alternativo se não existir largura de banda adequada no caminho primário. Desmarque essa caixa de seleção somente se você precisar desativar a descarga para a Internet. Se qualquer uma das suas chamadas serão chamadas pela Internet, esta caixa de seleção deve ser verificado, independentemente das configurações de largura de banda.

8.  A caixa de seleção **Habilitar vídeo caminho alternativo** está marcada por padrão. Esse campo determina se chamadas de vídeo serão roteadas por um caminho alternativo se não existir largura de banda adequada no caminho primário. Desmarque essa caixa de seleção somente se você precisar desativar a descarga para a Internet. Se qualquer uma das suas chamadas serão chamadas pela Internet, esta caixa de seleção deve ser verificado, independentemente das configurações de largura de banda.

9.  (Opcional) Digite um valor no campo **Descrição** para fornecer mais informações sobre essa região que não pode ser expressa somente pelo nome.

10. Clique em **Confirmar**.

A tabela de **sites associado** não é usada para criar uma região de rede. Você associa um site com uma região quando você cria ou modifica o site. Para obter detalhes, consulte [Gerenciando o controle de admissão de chamada para sites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Para modificar uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja modificar.

5.  No menu **Editar**, clique em **Exibir detalhes**.

6.  Na página **Editar região** , você pode modificar as configurações para habilitar e desabilitar áudio e vídeo alternam caminhos e alterar a descrição (para obter detalhes, consulte a seção "para criar uma região de rede" anteriormente contidas neste tópico.

7.  Clique em **Confirmar**.

Você não pode modificar os **sites associado** nesta página. A lista de sites associados é fornecida para referência, portanto você está ciente de que os sites que serão afetados quando você modifica as configurações de região.


## <a name="delete-existing-network-regions"></a>Excluir as regiões de rede existente 

Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas. Cada região de rede deve ser associado um site central. O site central é o site do Centro de dados no qual o serviço de política de largura de banda do chamada admissão CAC (controle) é executado. Você pode usar o Skype para painel de controle do Business Server para configurar regiões de rede. Regiões de rede incluem configurações que determinam se os caminhos alternativos através da Internet, são permitidos conexões de áudio e vídeo. Skype para painel de controle do Business Server, você pode criar, modificar ou excluir uma região de rede. Use este tópico para excluir as regiões de rede existente. 

### <a name="to-delete-a-network-region"></a>Para excluir uma região de rede

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **região**.

4.  Na página **região** , clique na região que você deseja excluir.
  
    > [!NOTE]  
    > Você pode excluir mais de uma região por vez. Para fazer isso, pressione CTRL e selecione várias regiões, mantendo pressionada a tecla CTRL. Ou, para selecionar todas as regiões, clique em **Selecionar tudo** no menu **Editar** .

5.  No menu **Editar** , clique em **Excluir**.

6.  Clique em **OK**.


    > [!WARNING]  
    > Uma região de rede não pode ser removida se estiver associada a um site de rede. Se você tentar remover uma região associada a um site, você receberá uma mensagem de erro. Para ver se uma região é associada a todos os sites, selecione a região e clique em **Mostrar detalhes** no menu **Editar** .


## <a name="see-also"></a>Consulte Também

[Gerenciando rotas de região de rede](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
