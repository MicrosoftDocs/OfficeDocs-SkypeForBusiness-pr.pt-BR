---
title: Requisitos de coleta de exemplo para controle de admissão de chamada Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: 'Fornece um exemplo detalhado de planejamento para o controle de admissão de chamada no Skype for Business Server Enterprise Voice, incluindo a coleta de informações sobre sites, regiões e largura de banda da sua rede.'
---

# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Exemplo: reunir requisitos para controle de admissão de chamada Skype for Business Server

Fornece um exemplo detalhado de planejamento para o controle de admissão de chamada no Skype for Business Server Enterprise Voice, incluindo a coleta de informações sobre sites, regiões e largura de banda da sua rede.

Este exemplo mostra como planejar e implementar o CAC (controle de admissão de chamadas). Em um alto nível, isso consiste nas seguintes atividades:

1. Identificar todos os seus hubs e backbones de rede (conhecidos como regiões de rede).

2. Identifique o Skype for Business Server local central que gerenciará o CAC para cada região de rede.

3. Identificar e definir os sites de rede conectados a cada região de rede.

4. Para cada site de rede cuja conexão com a WAN é restrita à largura de banda, descreva a capacidade de largura de banda da conexão WAN e os limites de largura de banda que o administrador de rede definiu para o tráfego de mídia Skype for Business Server, se aplicável. Não é necessário incluir sites cuja conexão com a WAN não sofra restrições de largura de banda.

5. Associe cada sub-rede em sua rede a um site de rede.

6. Mapeie os links entre as regiões de rede. Para cada link, descreva sua capacidade de largura de banda e quaisquer limites que o administrador de rede tenha colocado Skype for Business Server tráfego de mídia.

7. Defina uma rota entre cada par de regiões de rede.

## <a name="gather-the-required-information"></a>Colete as informações necessárias

Para se preparar para o controle de admissão de chamada, colete as informações descritas nas seguintes etapas:

1. Identifique suas regiões de rede. Uma região de rede representa um backbone de rede ou um hub de rede. 

    Um backbone de rede ou um hub de rede faz parte da infraestrutura de rede do computador que interconecta diversas peças da rede, fornecendo um caminho para a troca de informações entre LANs ou sub-redes diferentes. Um backbone pode unir diversas redes, de um pequeno local até uma área geográfica ampla. A capacidade do backbone é normalmente superior a da rede conectada a ele.

    Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém uma coleção de sites de rede. Trabalhe com seu administrador de rede para definir as regiões de rede para sua empresa.

2. Identifique o site central associado de cada região de rede. Um site central contém pelo menos um Servidor front-end e é a implantação Skype for Business Server que gerenciará o CAC para todo o tráfego de mídia que passa pela conexão WAN da região de rede.

   **Um exemplo de rede de empresa dividida em três regiões de rede**

     ![Exemplo de topologia de rede com 3 regiões de rede.](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Uma rede MPLS (Multiprotocol Label Switching) deve ser representada como uma região de rede na qual cada local geográfico tem um site de rede correspondente. Para obter detalhes, consulte [Components and toplogies for call admission control in Skype for Business](components-and-topologies.md). 

    No exemplo anterior de topologia de rede, há três regiões de rede, cada uma com um Skype for Business Server central que gerencia o CAC. O site central apropriado para uma região de rede é escolhido pela proximidade geográfica. Como o tráfego de mídia será o mais intenso nas regiões de rede, a propriedade por proximidade geográfica o tornará autocontido e continuará funcionando mesmo se outros sites centrais ficarem indisponíveis. 

    Neste exemplo, uma implantação Skype for Business chamada Chicago é o site central da região da América do Norte.

    Todos Skype for Business usuários na América do Norte estão em casa em servidores na implantação de Chicago. A tabela a seguir mostra os sites centrais de todas as três regiões de rede.

    **Regiões de rede e seus sites centrais associados**

    |**Região de rede**|**Site central**|
    |:-----|:-----|
    |América do Norte  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Pequim  <br/> |

    > [!NOTE]
    > Dependendo da topologia Skype for Business Server, o mesmo site central pode ser atribuído a várias regiões de rede. 

3. Para cada região de rede, identifique todos os sites de rede (escritórios ou locais) cujas conexões WAN não sofrem restrições de largura de banda. Como esses sites não sofrem restrições de largura de banda, não é necessário aplicar as políticas de largura de banda de CAC neles.

    No exemplo exibido na tabela abaixo, três sites de rede não têm links de WAN com restrição de largura de banda: Nova York, Chicago e Detroit.

   **Sites de rede sem restrições de largura de banda de WAN**


   | **Site de rede** | **Região de rede**   |
   |:-----------------|:---------------------|
   | Nova York  <br/>  | América do Norte  <br/> |
   | Chicago  <br/>   | América do Norte  <br/> |
   | Detroit  <br/>   | América do Norte  <br/> |


4. Para cada região de rede, identifique todos os sites de rede que se conectam à região de rede por meio de links de WAN com restrição de largura de banda.

    Para garantir a qualidade de áudio e vídeo, é recomendável que esses locais de rede com restrição de largura de banda tenham as WANs monitoradas e tenham políticas de largura de banda de CAC que limitem o tráfego de mídia (voz ou vídeo) de e para a região de rede.

    No exemplo exibido na tabela abaixo, há três sites de rede com restrição de largura de banda de WAN: Portland, Reno e Albuquerque.

   **Sites de rede com restrições de largura de banda de WAN**

   |**Site de rede**|**Região de rede**|
   |:-----|:-----|
   |Albuquerque  <br/> |América do Norte  <br/> |
   |Reno  <br/> |América do Norte  <br/> |
   |Portland  <br/> |América do Norte  <br/> |

   **Região de rede de CAC América do Norte com três sites de rede sem restrição de largura de banda (Chicago, Nova York e Detroit) e três sites de rede com restrição de largura de banda de WAN (Portland, Reno e Albuquerque)**

     ![Exemplo de sites de rede restritos pela largura de banda WAN.](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Para cada link de WAN com restrição de largura de banda, determine o seguinte:

   - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

   - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

   - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

   - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

     **Sites de rede com informações sobre restrição de largura de banda de WAN (largura de banda em kbps)**


     | **Site de rede**   | **Região de rede**   | **Limite de BW**      | **Limite de áudio**   | **Limite de sessão de áudio** | **Limite de vídeo**   | **Limite de sessão de vídeo** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | América do Norte  <br/> | 5.000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | América do Norte  <br/> | 10.000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | América do Norte  <br/> | 5.000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Nova York  <br/>    | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |
     | Chicago  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |
     | Detroit  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |


6. Para cada sub-rede em sua rede, especifique seu site de rede associado.

    > [!IMPORTANT]
    > Cada sub-rede em sua rede precisa estar associada a um site de rede, mesmo se o site de rede não sofrer restrição de largura de banda. Isso é devido ao controle de admissão de chamada usar as informações da sub-rede para determinar em qual site de rede um ponto de extremidade está localizado. Quando os locais de ambas as partes na sessão são determinados, o controle de admissão de chamada pode determinar se há largura de banda suficiente para estabelecer uma chamada. Quando uma sessão é estabelecida sobre um link que não possui limites de largura de banda, um alerta é gerado. 

    > [!IMPORTANT]
    > Se você implantar os Servidores de Borda de Áudio/Vídeo, os endereços IP públicos de cada Servidor de Borda deverão ser associados ao site externo no qual o Servidor de Borda está implantado. Cada endereço IP público do Servidor de Borda A/V precisa ser adicionado às suas configurações de rede como uma sub-rede com a máscara de sub-rede de 32. Por exemplo, se você implantar os Servidores de Borda A/V em Chicago, para cada endereço IP externo desses servidores, crie uma sub-rede com uma máscara de sub-rede de 32 e associe o site de rede Chicago a essas sub-redes. Para obter detalhes sobre endereços IP públicos, consulte [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md). 

    Um alerta de KHI (Key Health Indicator) é acionado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou a sub-rede que inclui os endereços IP não está associada a um site de rede. Esse alerta não será acionado novamente durante um período de oito horas. Veja a seguir as informações relevantes do alerta e um exemplo:

    **Fonte**: Serviço de Política de Largura de Banda (Principal) de CS 

    **Número do evento**: 36034

    **Nível**: 2

    **Descrição**: as sub-redes dos seguintes Endereços IP: \<List of IP Addresses\> não estão configuradas ou as sub-redes não estão associadas a um site de rede. 

    **Causa**: as sub-redes dos endereços IP correspondentes estão ausentes nas definições de configuração de rede ou as sub-redes não estão associadas a um site de rede. 

    **Resolução**: adicione sub-redes correspondentes à lista anterior de endereços IP nas definições de configuração de rede e associe todas as sub-redes a um site de rede.

    Por exemplo, a lista de endereços IP do alerta especifica 10.121.248.226 e 10.121.249.20. Esses dois endereços IP não estão associados a uma sub-rede ou a sub-rede a qual eles estão associados não pertence a um site de rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes desses endereços, será possível resolver esse problema da seguinte maneira:

    a. Certifique-se de que o endereço IP 10.121.248.226 esteja associado à sub-rede 10.121.248.0/24 e o endereço IP 10.121.249.20 esteja associado à sub-rede 10.121.249.0/24.

    b. Certifique-se de que cada uma das sub-redes 10.121.248.0/24 e 10.121.249.0/24 esteja associada a um site de rede.

   **Sites de rede e sub-redes associadas (largura de banda em kbps)**


   | **Site de rede**   | **Região de rede**   | **Limite de BW**      | **Limite de áudio**   | **Limite de sessão de áudio** | **Limite de vídeo**   | **Limite de sessão de vídeo** | **Sub-redes**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | América do Norte  <br/> | 5.000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | América do Norte  <br/> | 10.000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | América do Norte  <br/> | 5.000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | Nova York  <br/>    | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. No Skype for Business Server de admissão de chamadas, as conexões entre regiões de rede são chamadas de links de região. Para cada link de região, determine o seguinte, da mesma forma que fez para os sites de rede:

   - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

   - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

   - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

   - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

   **Links de região de rede com limites de largura de banda associados**

     ![Exemplo de limitações entre 3 regiões.](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Informações de largura de banda de link de região (largura de banda em kbps)**


   | **Nome do link de região**  | **Primeira região**     | **Segunda região** | **Limite de BW**  | **Limite de áudio** | **Limite de sessão de áudio** | **Limite de vídeo** | **Limite de sessão de vídeo** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | América do Norte  <br/> | EMEA  <br/>       | 50.000  <br/> | 20,000  <br/>   | 175  <br/>              | 14,000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25.000  <br/> | 10.000  <br/>   | 175  <br/>              | 7,000  <br/>    | 700  <br/>              |


8. Defina uma rota entre cada par de regiões de rede.

    > [!NOTE]
    > Dois links são necessários para a rota entre as regiões América do Norte e APAC, pois não há um link de região que as conecte diretamente. 

   **Rotas de região**


   | **Nome da rota de região**  | **Primeira região**     | **Segunda região** | **Links de região**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | América do Norte  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | América do Norte  <br/> | APAC  <br/>       | LINK-NA-EMEA, LINK-EMEA-APAC  <br/> |


9. Para cada par de sites de rede conectados diretamente por um único link (chamado de link entre sites), determine o seguinte:

     - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

     - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

     - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, Skype for Business Server não permitirá que a sessão inicie.

     - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

   **Região da rede CAC América do Norte mostrando as capacidades de largura de banda e limites de largura de banda para o link entre sites entre Reno e Albuquerque**

     ![Exemplo de sites de rede restritos por largura de banda wan.](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Informações de largura de banda para link entre sites entre dois sites de rede (largura de banda em kbps)**

   |**Nome do link entre sites**|**Primeiro site**|**Segundo site**|**Limite de BW**|**Limite de áudio**|**Limite de sessão de áudio**|**Limite de vídeo**|**Limite de sessão de vídeo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20,000  <br/> |12,000  <br/> |175  <br/> |5.000  <br/> |700  <br/> |

### <a name="next-steps"></a>Próximas Etapas

Depois de ter coletado as informações necessárias, você pode executar a implantação do CAC usando o Shell de Gerenciamento Skype for Business Server ou Skype for Business Server Painel de Controle.

> [!NOTE]
> Embora você possa executar a maioria das tarefas de configuração de rede usando Skype for Business Server Painel de Controle, para criar sub-redes e links entresites, você deve usar Skype for Business Server Shell de Gerenciamento. Para obter detalhes, [consulte New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps) e [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).