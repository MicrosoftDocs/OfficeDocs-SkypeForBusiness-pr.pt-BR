---
title: 'Implantar regiões de rede, sites e sub-redes em Skype for Business'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Crie ou modifique regiões de rede, sites de rede e associe sub-redes de rede Skype for Business Server. Todos eles são usados para os recursos avançados Enterprise Voice: bypass de mídia, controle de admissão de chamadas e roteamento baseado em local.'
---

# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Implantar regiões de rede, sites e sub-redes em Skype for Business

Crie ou modifique regiões de rede, sites de rede e associe sub-redes de rede Skype for Business Server. Todos eles são usados para os recursos avançados Enterprise Voice: bypass de mídia, controle de admissão de chamadas e roteamento baseado em local.

Os recursos Enterprise Voice avançados são [controle de](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) admissão de [chamadas, bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md) de [mídia,](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) roteamento baseado em local [e E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Todos esses recursos exigem que você crie regiões de rede, sites de rede e sub-redes. Por exemplo, todos esses recursos exigem que cada sub-rede em sua topologia seja associada a um site de rede específico, e cada site de rede deve ser associado a uma região de rede. Para obter mais informações sobre esses termos, consulte [Configurações de rede para os recursos de Enterprise Voice avançados no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).

O controle de admissão de chamada e o E9-1-1 têm requisitos de configuração adicionais para sites de rede:

- O controle de admissão de chamada exige que um perfil de política de largura de banda seja especificado para cada site restringido pelas limitações de largura de banda wan. Se você planeja implantar o controle de admissão de chamada, crie perfis de política de largura de [banda Skype for Business Server](create-bandwidth-policy-profiles.md) antes de configurar seus sites de rede.

- O E9-1-1 exige que uma política de local seja especificada para cada site. Se você planeja implantar o E9-1-1, crie políticas de localização no [Skype for Business Server antes de](create-location-policies.md) configurar seus sites de rede.

## <a name="create-or-modify-a-network-region"></a>Criar ou modificar uma região de rede

Se você já criou regiões de rede para um desses recursos, não precisa criar novas regiões de rede; outros recursos Enterprise Voice recursos avançados usarão essas mesmas regiões de rede.

Porém, talvez seja necessário modificar uma definição de região de rede existente para aplicar configurações específicas ao recurso. Por exemplo, se você cria regiões de rede para o E9-1-1 (que não exige um local central associado) e depois implanta o controle de admissão de chamadas, precisará modificar as definições de região de rede para especificar um local central.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Para criar uma região de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Execute o cmdlet New-CsNetworkRegion para criar regiões de rede:

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    Neste exemplo, você criou uma região de rede chamada "NorthAmerica" associada a um site central com a ID do site CHICAGO.

3. Para concluir a criação das regiões de rede para sua topologia, repita a etapa 2 com as configurações para cada região de rede.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Para criar uma região de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação à esquerda, clique em **Configuração de Rede**.

3. Clique em **Região**.

4. Clique em **Novo**.

5. Na página **Nova Região**, clique em **Nome** e digite um nome para a região de rede.

6. Clique em **Site central** e clique em um site central na lista.

7. Como opção, clique em **Descrição** e digite as informações adicionais para descrever esse site de rede.

8. Clique em **Confirmar**.

9. Para concluir a criação das regiões de rede para sua topologia, repita as etapas 4 a 8 com as configurações de outras regiões.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Para modificar uma região de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Execute o cmdlet Set-CsNetworkRegion para modificar uma região de rede existente:

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Por exemplo:

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    Neste exemplo, você modificou uma região de rede existente chamada "NorthAmerica" (criada usando os procedimentos anteriores neste tópico) alterando a descrição. Se uma descrição existisse para a região "NorthAmerica", esse comando a substituiria com esse valor; se nenhuma descrição tiver sido definida, este comando a definirá.

3. Para modificar outras regiões de rede, repita a etapa 2 com as configurações de outras regiões.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Para modificar uma região de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Configuração de Rede**.

3. Clique no botão de navegação **Região**.

4. Na tabela, clique na região de rede que você deseja modificar.

5. Clique em **Editar** e em **Mostrar detalhes…**.

6. Na página **Editar Região** , altere os valores das configurações dessa região de rede conforme apropriado.

7. Clique em **Confirmar**.

8. Para concluir a modificação das regiões de rede, repita as etapas 4 a 7 com as configurações de outras regiões.

## <a name="create-or-modify-a-network-site"></a>Criar ou modificar um site de rede

Se você já criou sites de rede para um desses recursos, não precisa criar novos sites de rede; outros recursos Enterprise Voice recursos avançados usarão esses mesmos sites de rede. Você pode, porém, precisar modificar uma definição de site de rede existente para aplicar configurações específicas do recurso. Por exemplo, se você criou um site de rede para o E9-1-1, você precisa modificar o site de rede durante a implantação do controle de admissão de chamada para aplicar um perfil de política de largura de banda.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para criar um site de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Execute o cmdlet do New-CsNetworkSite para criar sites de rede:

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    Neste exemplo, você criou um site de rede chamado "Chicago" que está na região de rede "NorthAmerica".

    > [!NOTE]
    > A região da rede NorthAmerica já deve existir para que esse comando seja executado com sucesso.

3. Para concluir a criação de sites de rede para a sua topologia, repita a etapa 2 com as configurações de outros sites.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para criar um site de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação à esquerda, clique em **Configurações de rede**.

3. Clique no botão de navegação **Site**.

4. Clique em **Novo**.

5. Na página **Novo Site**, clique em **Nome** e depois digite um nome para o site de rede.

6. Clique em **Região**, e depois clique em uma região na lista.

7. De modo opcional, clique em **Política de largura de banda** e depois clique em uma das larguras de banda da lista.

    > [!NOTE]
    > A política de largura de banda é solicitada apenas se você implantar o controle de admissão de chamada no site.

8. De modo opcional, clique em **Política de Local**, depois clique em uma política de local na lista.

    > [!NOTE]
    > A política de local é solicitada se você implantar E9-1-1 no site.

9. De modo opcional, clique em **Descrição**, e depois digite as informações adicionais para descrever o site de rede.

10. Clique em **Confirmar**.

11. Para concluir a criação de sites de rede para a sua topologia, repita as etapas 4 a 10 com as configurações de outros sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para modificar um site de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Execute o cmdlet Set-CsNetworkSite para modificar os sites de rede:

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    Por exemplo:

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    Neste exemplo, o site chamado "Albuquerque" é movido para a região de rede "NorthAmerica". Para modificar a configuração do site de rede para implantar o controle de admissão de chamada, o E9-1-1 ou desvio de mídia, modifique o site de rede executando o cmdlet Set-CsNetworkSite ou com os parâmetros do BWPolicyProfileID ou do LocationPolicy, respectivamente.

    > [!NOTE]
    > Embora o parâmetro do BypassID exista para o desvio de mídia, recomendamos que você não sobreponha IDs de desvio geradas automaticamente. Você não precisa especificar parâmetros adicionais para configurar um site de rede para o desvio de mídia.

3. Para concluir a modificação dos sites de rede para sua topologia, repita a etapa 2 com as configurações de outros sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para modificar um site de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação à esquerda, clique em **Configurações de rede**.

3. Clique no botão de navegação **Site**.

4. Na tabela, clique no site de rede que você quer modificar.

5. Clique em **Editar**, e depois clique em **Mostra detalhes…**.

6. Na página **Editar Site** , altere os valores para as configurações desse site de rede conforme apropriado.

7. Clique em **Confirmar**.

8. Para concluir a modificação de sites de rede, repita as etapas de 4 a 7 com configurações de outros sites.

## <a name="associate-a-subnet-with-a-network-site"></a>Associar uma sub-rede a um site de rede
<a name="BKMK_AssociateSubnets"> </a>

Todas as sub-redes da sua rede devem ser associadas a um local de rede específico, pois as informações da sub-rede são usadas para determinar o local de rede em que um ponto de extremidade se encontra quando uma nova sessão é iniciada. Quando o local de cada parte em uma sessão é conhecido, os recursos de Enterprise Voice avançados podem aplicar essas informações para determinar como lidar com a configuração ou o roteamento de chamadas.

Todos os endereços IP públicos configurados dos Servidores de Borda de Áudio/Vídeo em sua implantação devem ser adicionados às suas definições de configuração de rede. Estes endereços IP são adicionados como sub-redes com uma máscara de 32. O site de rede associado deve corresponder ao site de rede configurado adequado. Por exemplo, o endereço IP público que corresponde ao serviço de Borda A/V no site central Chicago seria NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Para associar uma sub-rede a um site de rede usando Skype for Business Server Shell de Gerenciamento

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

2. Execute o cmdlet **New-CsNetworkSubnet** para associar uma sub-rede a um site da rede:

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Por exemplo:

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    Neste exemplo, você criou uma associação entre a sub-rede 172.11.12.13 e o site de rede "Chicago".

3. Repita a etapa 2 para todas as sub-redes em sua topologia.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Para associar sub-redes a sites da rede importando um arquivo CSV

1. Crie um arquivo CSV que inclui todas as sub-redes que deseja adicionar. Por exemplo, crie um arquivo chamado **subnet.csv** como o seguinte conteúdo:

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.

3. Execute o seguinte cmdlet **para importarsubnet.csv** e, em seguida, armazene seu conteúdo no armazenamento de gerenciamento do Lync Server:

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Para associar uma sub-rede a um site de rede usando Skype for Business Server Painel de Controle

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação à esquerda, clique em **Configuração da Rede**.

3. Clique no botão de navegação **Sub-rede**.

4. Clique em **Novo**.

5. Na página **Nova Sub-rede**, clique em **ID da Sub-rede** e digite o primeiro endereço do intervalo de endereços IP definido pela sub-rede que deseja associar a um site da rede.

6. Clique em **Máscara** e digite o bitmask a ser aplicado à sub-rede.

7. Clique em **ID do site da rede** e selecione o ID do site para o qual está adicionando esta sub-rede.

    > [!NOTE]
    > Se sites da rede ainda não estiverem criados, a lista estará vazia. Para obter detalhes sobre o procedimento, consulte [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site). Você também pode configurar IDs de site para a sua implantação executando o cmdlet **Get-CsNetworkSite**. Para obter detalhes, consulte a documentação Skype for Business Server Shell de Gerenciamento.

8. Opcionalmente, clique em **Descrição** e digite informações adicionais para descrever esta sub-rede.

9. Clique em **Confirmar**.

Repita estas etapas para adicionar outras sub-redes a um site da rede.
> [!NOTE]
> Um alerta Key Health Indicator (KHI) é disparado, especificando uma lista de endereços IP presentes em sua rede mas que não estão associados a uma sub-rede ou à sub-rede que inclui os endereços IP não está associada a um site de rede. Este alerta não será disparado mais de uma vez dentro de um período de 8 horas.

A informação de alerta relevante e um exemplo são como segue:

 **Fonte**: Serviço de Política de Largura de Banda (Principal) de CS

 **Número do evento**: 36034

 **Nível**: 2

 **Descrição**: as sub-redes dos seguintes endereços IP: \<List of IP Addresses\> não estão configuradas ou as sub-redes não estão associadas a um Site de Rede.

 **Causa**: as sub-redes para os endereços IP correspondentes estão ausentes nas definições de configuração da rede ou as sub-redes não estão associadas a um site da rede.

 **Solução**: adicione sub-redes correspondentes à lista de endereços IP nas definições de configuração da rede e associe todas as sub-redes a um site da rede.

Por exemplo, se a lista de endereços IP no alerta especificar 10.121.248.226 e 10.121.249.20, ou estes endereços IP não estão associados a uma sub-rede ou a sub-rede à qual estão associados não pertence a um site da rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes para estes endereços, você pode resolver o problema da seguinte forma:

1. Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.

2. Certifique-se de que cada uma das sub-redes 10.121.248.0/24 e 10.121.249.0/24 esteja associada a um site de rede.

## <a name="see-also"></a>Confira também
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)