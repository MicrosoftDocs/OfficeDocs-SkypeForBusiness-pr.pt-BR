---
title: Exemplo de coleta de requisitos para controle de admissão de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Fornece um exemplo detalhado de planejamento para o controle de admissão de chamadas no Skype for Business Server Enterprise Voice, incluindo a coleta de informações sobre sites, regiões e largura de banda de sua rede.
ms.openlocfilehash: bf33c70120adb65c88a6be05d2c04bf55e989b72
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802881"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Exemplo: coletando requisitos para o controle de admissão de chamadas no Skype for Business Server

Fornece um exemplo detalhado de planejamento para o controle de admissão de chamadas no Skype for Business Server Enterprise Voice, incluindo a coleta de informações sobre sites, regiões e largura de banda de sua rede.

Este exemplo mostra como planejar e implementar o CAC (controle de admissão de chamadas). Em um alto nível, isso consiste nas seguintes atividades:

1. Identificar todos os hubs e backbones de rede (conhecidos como regiões de rede).

2. Identifique o site central do Skype for Business Server que irá gerenciar o CAC para cada região de rede.

3. Identificar e definir os locais de rede conectados a cada região de rede.

4. Para cada site de rede cuja conexão à WAN é restrita à largura de banda, descreva a capacidade de largura de banda da conexão WAN e os limites de largura de banda que o administrador de rede definiu para o tráfego de mídia do Skype for Business Server, se aplicável. Não é necessário incluir locais cuja conexão com a WAN não tenha restrição de largura de banda.

5. Associe cada sub-rede de sua rede a um local de rede.

6. Mapeie os links entre as regiões de rede. Para cada link, descreva a capacidade de largura de banda e os limites que o administrador da rede colocou no tráfego de mídia do Skype for Business Server.

7. Defina uma rota entre cada par de regiões de rede.

## <a name="gather-the-required-information"></a>Colete as informações necessárias

Para se preparar para o controle de admissão de chamada, colete as informações descritas nas seguintes etapas:

1. Identifique suas regiões de rede. Uma região de rede representa um backbone de rede ou um hub de rede. 

    Um backbone de rede ou um hub de rede faz parte da infraestrutura de rede do computador que interconecta diversas partes da rede, fornecendo um caminho para a troca de informações entre LANs ou sub-redes diferentes. Um backbone pode unir redes distintas, de um pequeno local até uma ampla área geográfica. A capacidade do backbone é normalmente superior à da rede conectada a ele.

    Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém uma coleção de locais de rede. Trabalhe com seu administrador de rede para definir as regiões de rede para sua empresa.

2. Identifique o site central associado a cada região de rede. Um site central contém pelo menos um servidor front-end e é a implantação do Skype for Business Server que gerenciará o CAC para todo o tráfego de mídia que passar pela conexão WAN da região de rede.

   **Um exemplo de rede de empresa dividida em três regiões de rede**

     ![Exemplo de topologia de rede com 3 regiões de rede](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Uma rede MPLS deve ser representada como uma região de rede na qual cada local geográfico tem um local de rede correspondente. Para obter detalhes, consulte [componentes e topologias para controle de admissão de chamadas no Skype for Business](components-and-topologies.md). 

    Na topologia de rede de exemplo anterior, há três regiões de rede, cada uma com um site central do Skype for Business Server que gerencia o CAC. O local central apropriado para uma região de rede é escolhido pela proximidade geográfica. Como o tráfego de mídia será o mais intenso nas regiões de rede, a propriedade por proximidade geográfica o tornará autocontido e continuará funcionando mesmo que outros locais centrais fiquem indisponíveis. 

    Neste exemplo, uma implantação do Skype for Business chamada Chicago é o site central da região da América do Norte.

    Todos os usuários do Skype for Business na América do Norte são hospedados em servidores na implantação de Chicago. A tabela a seguir mostra os locais centrais de todas as três regiões de rede.

    **Regiões de rede e locais centrais associados**

    |**Região de rede**|**Local central**|
    |:-----|:-----|
    |América do Norte  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Pequim  <br/> |

    > [!NOTE]
    > Dependendo da topologia do Skype for Business Server, o mesmo site central pode ser atribuído a várias regiões de rede. 

3. Para cada região de rede, identifique todos os locais de rede (escritórios ou locais) cujas conexões WAN não sofrem restrições de largura de banda. Como esses locais não sofrem restrições de largura de banda, não é necessário aplicar as políticas de largura de banda de CAC a eles.

    No exemplo exibido na tabela abaixo, três locais de rede não têm links WAN com restrição de largura de banda: Nova York, Chicago e Detroit.

   **Locais de rede sem restrições de largura de banda de WAN**


   | **Site de rede** | **Região de rede**   |
   |:-----------------|:---------------------|
   | Nova York  <br/>  | América do Norte  <br/> |
   | Chicago  <br/>   | América do Norte  <br/> |
   | Detroit  <br/>   | América do Norte  <br/> |


4. Para cada região de rede, identifique todos os locais de rede que se conectam à região de rede por meio de links WAN com restrição de largura de banda.

    Para garantir a qualidade de áudio e vídeo, é recomendável que esses locais de rede com restrição de largura de banda tenham as WANs monitoradas e tenham políticas de largura de banda de CAC que limitem o tráfego de mídia (voz ou vídeo) de e para a região de rede.

    No exemplo exibido na tabela abaixo, há três locais de rede com restrição de largura de banda de WAN: Portland, Reno e Albuquerque.

   **Locais de rede com restrições de largura de banda de WAN**

   |**Site de rede**|**Região de rede**|
   |:-----|:-----|
   |Albuquerque  <br/> |América do Norte  <br/> |
   |Reno  <br/> |América do Norte  <br/> |
   |Portland  <br/> |América do Norte  <br/> |

   **Região de rede de CAC América do Norte com três sites de rede sem restrição de largura de banda (Chicago, Nova York e Detroit) e três sites de rede com restrição de largura de banda de WAN (Portland, Reno e Albuquerque)**

     ![Exemplo de sites de rede restritos pela largura de banda WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Para cada link de WAN com restrição de largura de banda, determine o seguinte:

   - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

   - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

   - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

   - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

     **Locais de rede com informações sobre restrição de largura de banda de WAN (largura de banda em kbps)**


     | **Site de rede**   | **Região de rede**   | **Limite de BW**      | **Limite de áudio**   | **Limite de sessão de áudio** | **Limite de vídeo**   | **Limite de sessão de vídeo** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | América do Norte  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1.400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | América do Norte  <br/> | 10.000  <br/>     | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | América do Norte  <br/> | 5.000  <br/>      | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              |
     | Nova York  <br/>    | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |
     | Chicago  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |
     | Detroit  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       |


6. Para cada sub-rede em sua rede, especifique seu local de rede associado.

    > [!IMPORTANT]
    > Cada sub-rede em sua rede precisa estar associada a um local de rede, mesmo se o local de rede não sofrer restrição de largura de banda. Isso é devido ao controle de admissão de chamada usar as informações da sub-rede para determinar em qual local de rede um ponto de extremidade está localizado. Quando os locais de ambas as partes na sessão são determinados, o controle de admissão de chamada pode determinar se há largura de banda suficiente para estabelecer uma chamada. Quando uma sessão é estabelecida sobre um link que não possui limites de largura de banda, um alerta é gerado. 

    > [!IMPORTANT]
    > Se você implantar Servidores de Borda de Áudio/Vídeo, os endereços IP públicos de cada Servidor de Borda deverão ser associados ao local externo no qual o Servidor de Borda está implantado. Cada endereço IP público do Servidor de Borda A/V deve ser adicionado aos seus parâmetros de configuração de rede como uma sub-rede com uma máscara de sub-rede 32. Por exemplo, se você implantar Servidores de Borda A/V em Chicago, para cada endereço IP externo desses servidores, crie uma sub-rede com uma máscara de sub-rede 32 e associe o local de rede Chicago a essas sub-redes. Para obter detalhes sobre endereços IP públicos, consulte [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md) na documentação Planejamento. 

    Um alerta KHI (Key Health Indicator) é acionado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede, ou a sub-rede que inclui os endereços IP não está associada a um local de rede. Esse alerta não será acionado novamente durante um período de oito horas. Veja a seguir as informações relevantes do alerta e um exemplo:

    **Origem**: Serviço de Política de Largura de Banda CS (Núcleo) 

    **Número do evento**: 36034

    **Nível**: 2

    **Descrição**: as sub-redes dos seguintes endereços IP: \<a lista de endereços\> IP não estão configurados ou as sub-redes não estão associadas a um site de rede. 

    **Causa**: as sub-redes para os endereços IP correspondentes estão ausentes nos parâmetros de configuração de rede ou as sub-redes não estão associadas a um local de rede. 

    **Resolução**: adicione sub-redes correspondentes à lista anterior de endereços IP nos parâmetros de configuração de rede e associe todas as sub-redes a um local de rede.

    Por exemplo, a lista de endereços IP do alerta especifica 10.121.248.226 e 10.121.249.20. Esses dois endereços IP não estão associados a uma sub-rede, ou a sub-rede à qual eles estão associados não pertence a um local de rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes desses endereços, será possível resolver esse problema da seguinte maneira:

    a. Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.

    b. Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um site da rede.

   **Locais de rede e sub-redes associadas (largura de banda em kbps)**


   | **Site de rede**   | **Região de rede**   | **Limite de BW**      | **Limite de áudio**   | **Limite de sessão de áudio** | **Limite de vídeo**   | **Limite de sessão de vídeo** | **Sub-redes**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | América do Norte  <br/> | 5.000  <br/>      | 2.000  <br/>      | 175  <br/>              | 1.400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | América do Norte  <br/> | 10.000  <br/>     | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | América do Norte  <br/> | 5.000  <br/>      | 4.000  <br/>      | 175  <br/>              | 2.800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | Nova York  <br/>    | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Chicago  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | América do Norte  <br/> | (sem limite)  <br/> | (sem limite)  <br/> | (sem limite)  <br/>       | (sem limite)  <br/> | (sem limite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. No controle de admissão de chamadas do Skype for Business Server, as conexões entre regiões de rede são chamadas de links de região. Para cada link de região, determine o seguinte, da mesma forma que fez para os locais de rede:

   - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

   - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

   - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

   - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

   **Links de região de rede com limites de largura de banda associados**

     ![Exemplo de limitações entre 3 regiões](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Informações de largura de banda de link de região (largura de banda em kbps)**


   | **Nome do link de região**  | **Primeira região**     | **Segunda região** | **Limite de BW**  | **Limite de áudio** | **Limite de sessão de áudio** | **Limite de vídeo** | **Limite de sessão de vídeo** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | LINK-NA-EMEA  <br/>   | América do Norte  <br/> | EMEA  <br/>       | 50.000  <br/> | 20.000  <br/>   | 175  <br/>              | 14.000  <br/>   | 700  <br/>              |
   | LINK-EMEA-APAC  <br/> | EMEA  <br/>          | APAC  <br/>       | 25.000  <br/> | 10.000  <br/>   | 175  <br/>              | 7.000  <br/>    | 700  <br/>              |


8. Defina uma rota entre cada par de regiões de rede.

    > [!NOTE]
    > Dois links são necessários para a rota entre as regiões América do Norte e APAC, pois não há um link de região que as conecte diretamente. 

   **Rotas de região**


   | **Nome da rota de região**  | **Primeira região**     | **Segunda região** | **Links de região**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | ROTA-NA-EMEA  <br/>   | América do Norte  <br/> | EMEA  <br/>       | LINK-NA-EMEA  <br/>                 |
   | ROTA-EMEA-APAC  <br/> | EMEA  <br/>          | APAC  <br/>       | LINK-EMEA-APAC  <br/>               |
   | ROTA-NA-APAC  <br/>   | América do Norte  <br/> | APAC  <br/>       | LINK-NA-EMEA, LINK-EMEA-APAC  <br/> |


9. Para cada par de locais de rede conectados diretamente por um único link (chamado de link entre locais), determine o seguinte:

     - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

     - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.

     - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Skype for Business Server não permitirá que a sessão seja iniciada.

     - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.

   **Região da rede CAC América do Norte mostrando as capacidades de largura de banda e limites de largura de banda para o link entre sites entre Reno e Albuquerque**

     ![Sites de rede restritos pelo exemplo de largura de banda de WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Informações de largura de banda para link entre locais entre dois locais de rede (largura de banda em kbps)**

   |**Nome do link entre locais**|**Primeiro local**|**Segundo local**|**Limite de BW**|**Limite de áudio**|**Limite de sessão de áudio**|**Limite de vídeo**|**Limite de sessão de vídeo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Link-entre-locais-Reno-Albu  <br/> |Reno  <br/> |Albuquerque  <br/> |20.000  <br/> |12.000  <br/> |175  <br/> |5.000  <br/> |700  <br/> |

### <a name="next-steps"></a>Próximas etapas

Depois de coletar as informações necessárias, você pode executar a implantação do CAC usando o Shell de gerenciamento do Skype for Business Server ou o painel de controle do Skype for Business Server.

> [!NOTE]
> Embora seja possível executar a maioria das tarefas de configuração de rede usando o painel de controle do Skype for Business Server, para criar sub-redes e links entre sites, você deve usar o Shell de gerenciamento do Skype for Business Server. Para obter detalhes, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 


