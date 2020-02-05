---
title: Implantar regiões de rede, sites e sub-redes no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Crie ou modifique regiões de rede, sites de rede e associe sub-redes de rede no Skype for Business Server. Todas elas são usadas para os recursos avançados de voz empresarial: bypass de mídia, controle de admissão de chamadas e roteamento baseado em local.'
ms.openlocfilehash: e181e8fffc431db67e0e597f3e8dccba710efdd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767514"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Implantar regiões de rede, sites e sub-redes no Skype for Business

Crie ou modifique regiões de rede, sites de rede e associe sub-redes de rede no Skype for Business Server. Todas elas são usadas para os recursos avançados de voz empresarial: bypass de mídia, controle de admissão de chamadas e roteamento baseado em local.

Os recursos avançados de voz empresarial [são controle de admissão de chamadas](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), bypass de [mídia](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [roteamento baseado em local](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)e [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Esses recursos todos exigem que você crie regiões da rede, sites da redee sub-redes. Por exemplo, todos estes recursos requerem que cada sub-rede em sua topologia seja associada a um local de rede específico, e cada site da rede deve ser associado a uma região da rede. Para obter mais informações sobre estes termos, consulte [configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).

O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para os sites da rede:

- O serviço de controle de admissão de chamadas requer que um perfil de política de largura de banda seja especificado para cada site restrito pelas limitações de largura de banda WAN. Se você planeja implantar o controle de admissão de chamadas, deverá [criar perfis de política de largura de banda no Skype for Business Server](create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.

- O E9-1-1 requer que uma política local seja especificada para cada site. Se você planeja implantar o E9-1-1, será necessário [criar políticas de localização no Skype for Business Server](create-location-policies.md) antes de configurar seus sites de rede.

## <a name="create-or-modify-a-network-region"></a>Criar ou modificar uma região da rede

Se você já tiver criado regiões de rede para um desses recursos, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.

No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Para criar uma região de rede usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute o cmdlet New-CsNetworkRegion para criar regiões da rede:

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    Neste exemplo, você criou uma região de rede chamada "América do oeste" que está associada a um site central com a ID de site CHICAGO.

3. Para concluir a criação das regiões de rede para sua topologia, repita a etapa 2 com as configurações para cada região da rede.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Para criar uma região de rede usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Configuração de rede**.

3. Clique em **Região**.

4. Clique em **Novo**.

5. Na página **Nova Região**, clique em **Nome** e digite um nome para a região da rede.

6. Clique em **Site central** e, em seguida, clique em um site central na lista.

7. Como opção, clique em **Descrição** e digite as informações adicionais para descrever esse site da rede.

8. Clique em **Confirmar**.

9. Para concluir a criação das regiões da rede para sua topologia, repita as etapas 4 a 8 com as configurações de outras regiões.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Para modificar uma região de rede usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute o cmdlet Set-CsNetworkRegion para modificar uma região da rede existente:

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por exemplo:

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    Neste exemplo, você modificou uma região de rede existente chamada "América do país" (criada usando os procedimentos anteriores neste tópico) alterando a descrição. Se existe uma descrição para a região "América do país", esse comando substitui esse valor; Se nenhuma descrição tiver sido definida, esse comando a definirá.

3. Para modificar outras regiões da rede, repita a etapa 2 com as configurações de outras regiões.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Para modificar uma região de rede usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Configuração de rede**.

3. Clique no botão de navegação **Região**.

4. Na tabela, clique na região da rede que você deseja modificar.

5. Clique em **Editar** e, em seguida, clique em **Mostrar detalhes…**.

6. Na página **Editar região** , altere os valores das configurações da região de rede conforme apropriado.

7. Clique em **Confirmar**.

8. Para concluir a modificação das regiões da rede, repita as etapas 4 a 7 com as configurações de outras regiões.

## <a name="create-or-modify-a-network-site"></a>Criar ou modificar um site da rede

Se você já tiver criado sites de rede para um desses recursos, não precisará criar novos sites de rede; outros recursos avançados do Enterprise Voice usarão esses mesmos sites de rede. Você pode, porém, precisar modificar uma definição de site da rede existente para aplicar configurações específicas do recurso. Por exemplo, se você criou um site da rede para o E9-1-1, você precisa modificar o site da rede durante a implantação do serviço de controle de admissão de chamadas para aplicar um perfil de política de largura de banda.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para criar um site de rede usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute o cmdlet do New-CsNetworkSite para criar sites da rede:

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    Neste exemplo, você criou um site de rede chamado "Chicago" que está na região de rede "América do país".

    > [!NOTE]
    > A região da rede NorthAmerica já deve existir para que esse comando seja executado com sucesso.

3. Para concluir a criação de sites da rede para a sua topologia, repita a etapa 2 com as configurações de outros sites.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para criar um site de rede usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Configuração de rede**.

3. Clique no botão de navegação **Site**.

4. Clique em **Novo**.

5. Na página **Novo Site**, clique em **Nome** e depois digite um nome para o site da rede.

6. Clique em **Região**, e depois clique em uma região na lista.

7. De modo opcional, clique em **Política de largura de banda**, e depois clique em uma das larguras de banda da lista.

    > [!NOTE]
    > A política de largura de banda é solicitada apenas se você implantar o serviço de controle de admissão de chamadas no site.

8. De modo opcional, clique em **Política de Local**, depois clique em uma política de local na lista.

    > [!NOTE]
    > A política de local é solicitada se você implantar E9-1-1 no site.

9. Como opção, clique em **Descrição**, em seguida, digite as informações adicionais para descrever esse site da rede.

10. Clique em **Confirmar**.

11. Para concluir a criação de sites da rede para a sua topologia, repita as etapas 4 a 10 com as configurações de outros sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para modificar um site de rede usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute o cmdlet Set-CsNetworkSite para modificar os sites da rede:

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    Por exemplo:

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    Neste exemplo, o site chamado "Albuquerque" é movido para a região de rede "América do país". Para modificar a configuração do site da rede para implantar o serviço de controle de admissão de chamadas, o E9-1-1 ou desvio de mídia, modifique o site da rede executando o cmdlet Set-CsNetworkSite com os parâmetros do BWPolicyProfileID ou LocationPolicy, respectivamente.

    > [!NOTE]
    > Embora o parâmetro do BypassID exista para o desvio de mídia, recomendamos que você não sobreponha IDs de desvio geradas automaticamente. Você não precisa especificar parâmetros adicionais para configurar um site da rede para o desvio de mídia.

3. Para concluir a modificação dos sites da rede para sua topologia, repita a etapa 2 com as configurações de outros sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para modificar um site de rede usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Configuração de rede**.

3. Clique no botão de navegação **Site**.

4. Na tabela, clique no site da rede que você quer modificar.

5. Clique em **Editar**e, em seguida, clique em **Mostrar detalhes…**.

6. Na página **Editar site** , altere os valores para as configurações do site de rede conforme apropriado.

7. Clique em **Confirmar**.

8. Para concluir a modificação de sites da rede, repita as etapas de 4 a 7 com configurações de outros sites.

## <a name="associate-a-subnet-with-a-network-site"></a>Associar uma subrede a um site da rede
<a name="BKMK_AssociateSubnets"> </a>

Todas as sub-redes da sua rede devem ser associadas a um site da rede específico, pois as informações da sub-rede são usadas para determinar o site da rede em que um ponto de extremidade se encontra quando uma nova sessão é iniciada. Quando o local de cada participante de uma sessão é conhecido, recursos avançados do Enterprise Voice podem aplicar essas informações para determinar como manipular a configuração ou o roteamento de chamadas.

Todos os endereços IP públicos configurados dos Servidores de Borda de Áudio/Vídeo em sua implantação devem ser adicionados às suas definições de configuração da rede. Estes endereços IP são adicionados como sub-redes com uma máscara de 32. O site da rede associado deve corresponder ao site da rede configurado adequado. Por exemplo, o endereço IP público que corresponde ao serviço de borda A/V no site central de Chicago seria NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para associar uma sub-rede a um site de rede usando o Shell de gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

2. Execute o cmdlet  **New-CsNetworkSubnet** para associar uma sub-rede a um site da rede:

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    Neste exemplo, você criou uma associação entre a 172.11.12.13 de sub-rede e o site de rede "Chicago".

3. Repita a etapa 2 para todas as sub-redes em sua topologia.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Para associar sub-redes a sites da rede importando um arquivo CSV

1. Crie um arquivo CSV que inclui todas as sub-redes que deseja adicionar. Por exemplo, crie um arquivo chamado **subnet.csv** como o seguinte conteúdo:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Execute o cmdlet a seguir para importar o **subnet. csv**e, em seguida, armazenar seu conteúdo na loja de gerenciamento do Lync Server:

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para associar uma sub-rede a um site de rede usando o painel de controle do Skype for Business Server

1. Abra o painel de controle do Skype for Business Server.

2. Na barra de navegação esquerda, clique em **Configuração de rede**.

3. Clique no botão de navegação **Sub-rede**.

4. Clique em **Novo**.

5. Na página **Nova Sub-rede**, clique em **ID da Sub-rede** e digite o primeiro endereço do intervalo de endereços IP definido pela sub-rede que deseja associar a um site da rede.

6. Clique em **Máscara** e digite o bitmask a ser aplicado à sub-rede.

7. Clique em **ID do site da rede** e selecione o ID do site para o qual está adicionando esta sub-rede.

    > [!NOTE]
    > Se os sites da rede ainda não estiverem criados, a lista estará vazia. Para obter detalhes sobre o procedimento, consulte [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). Você também pode recuperar as IDs do site para sua implantação executando o cmdlet **Get-CsNetworkSite**. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Skype for Business Server.

8. Opcionalmente, clique em  **Descrição** e digite informações adicionais para descrever esta sub-rede.

9. Clique em **Confirmar**.

Repita estas etapas para adicionar outras sub-redes a um site da rede.
> [!NOTE]
> Um alerta Key Health Indicator (KHI) é disparado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou à sub-rede que inclui os endereços IP não está associada a um site da rede. Este alerta não será disparado mais de uma vez dentro de um período de 8 horas.

A informação de alerta relevante e um exemplo são como segue:

 **Origem**: Serviço de Política de Largura de Banda CS (Núcleo)

 **Número do evento**: 36034

 **Nível**: 2

 **Descrição**: as sub-redes dos seguintes endereços IP: \<a lista de endereços\> IP não estão configurados ou as sub-redes não estão associadas a um site de rede.

 **Causa**: as sub-redes para os endereços IP correspondentes estão ausentes nos parâmetros de configuração de rede ou as sub-redes não estão associadas a um site da rede.

 **Solução**: adicione sub-redes correspondentes à lista de endereços IP nas definições de configuração da rede e associe todas as sub-redes a um site da rede.

Por exemplo, se a lista de endereços IP no alerta especifica 10.121.248.226 e 10.121.249.20, ou estes endereços IP não estão associados a uma sub-rede ou a sub-rede à qual estão associados não pertence a um site da rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes para estes endereços, você pode resolver o problema da seguinte forma:

1. Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.

2. Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um site da rede.

## <a name="see-also"></a>Confira também
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

