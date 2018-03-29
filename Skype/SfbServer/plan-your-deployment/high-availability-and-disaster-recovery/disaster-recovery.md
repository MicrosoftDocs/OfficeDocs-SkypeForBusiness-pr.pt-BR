---
title: Recuperação de desastre do pool de Front-Ends no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Recuperação de desastres, Skype para Business Server oferece pareamento com failover no caso de um pool cair do pool.
ms.openlocfilehash: 50f4b7b37ed6b3f0aefb9c44736c6415054604f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server-2015"></a>Recuperação de desastre do pool de Front-Ends no Skype for Business Server 2015
 
Recuperação de desastres, Skype para Business Server oferece pareamento com failover no caso de um pool cair do pool.
  
Para as mais robustas opções recuperação de desastres no Skype para Business Server, implante o pares de pools de Front-End entre dois sites geograficamente dispersos. Cada site tem um Pool de Front-Ends emparelhado com um Pool de Front-Ends correspondente no outro site. Os dois sites estão ativos, e o Serviço de Backup oferece replicação de dados em tempo real para manter os pools sincronizados. Consulte [Deploy emparelhada pools de Front-End para recuperação de desastres em Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) se você quiser implementar o pareamento de pool de Front-End.
  
![Mostra Pools de Front-End em dois sites diferentes, emparelhados](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Se o pool em um local falhar, é possível fazer failover dos usuários desse pool para o pool no outro local, que atende a todos os usuários em ambos os pools. Para fins de planejamento de capacidade, você deve projetar cada pool para lidar com a carga de trabalho de todos os usuários em ambos os pools em caso de desastre.
  
Dois data centers que incluem Pools de Front-Ends emparelhados podem estar a qualquer distância um do outro. Recomendamos que os dois data centers sejam emparelhados na mesma região do mundo, com links de alta velocidade entre eles. 
  
Ter dois data centers em regiões geográficas distintas é possível, mas poderia incorrer maior perda de dados, se houver um desastre, devido à latência na replicação dos dados.
  
Quando você planejar quais pools emparelhar, você deve ter em mente que que somente os emparelhamentos a seguir são suportados:
  
- Os pools Enterprise Edition podem ser emparelhados somente com outros pools Enterprise Edition. Da mesma forma, pools Standard Edition podem ser emparelhados somente com outros pools Standard Edition.
    
- Os pools físicos somente podem ser emparelhados com outros pools físicos. Da mesma forma, os pools virtuais somente podem ser emparelhados com outros pools virtuais.
    
- Pools que são pareados juntos devem estar executando o mesmo sistema operacional de base.
    
Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas. Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool Enterprise Edition com um pool Standard Edition. No entanto, estes tipos de emparelhamentos não são aceitos.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relações do registrador de backup e aparelhos de filial persistente

Além de permitir a recuperação de desastre, dois pools emparelhados atuam como os Registradores de backup entre si. Cada pool pode ser o backup para apenas um outro pool de Front-End.
  
Embora as relações de backup entre dois pools de Front-End devem ser 1:1 e simétricas, cada pool de Front-End ainda pode ser o registrador de backup para qualquer número de aparelhos de filial persistente.
  
Observe que o Skype for Business não estende o suporte de recuperação de desastre a usuários hospedados em um Aparelho de Filial Persistente. Se um Pool de Front-Ends que atua como o backup para um Aparelho de Filial Persistente sair do ar, os usuários conectados ao Aparelho de Filial Resistente entrarão no modo de resiliência mesmo que seja feito o failover dos usuários hospedados no Pool de Front-Ends para o backup do Pool de Front-End.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tempo de recuperação para failover e failback de pool

Para failover e failback de pool, o destino projetado para objetivo de tempo de recuperação (RTO) é de 15 a 20 minutos. Este é o tempo necessário para o failover acontecer, após os administradores terem determinado que houve um desastre e iniciarem os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomarem uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.
  
Para failover e failback de pool, o destino projetado para objetivo de ponto de recuperação (RPO) é de 5 minutos. Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup. Por exemplo, se um pool cair às 10:00 e o RPO é de 5 minutos, os dados gravados para o pool entre 9:55:00 e .might 10:00 A.M. não têm replicados para o pool de backup e serão perdidos.
  
Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região do mundo com alta velocidade e transporte de baixa latência entre os dois locais. Esses números são medidos para um pool com 40.000 usuários ativos ao mesmo tempo e 200.000 usuários habilitados para Lync com respeito a um modelo de usuário predefinido, onde não há backlog na replicação de dados. Eles estão sujeitos a alteração baseado no teste e na validação de desempenho.
  
## <a name="central-management-store-failover"></a>Failover do Repositório de Gerenciamento Central

O Repositório de Gerenciamento Central contém dados de configuração sobre os servidores e serviços de sua implantação. Cada Skype para implantação Business Server inclui um repositório de gerenciamento Central, que é hospedado pelo servidor Back-End de um pool de Front-End.
  
Se você emparelhar o pool que hospeda o Repositório de Gerenciamento Central, um banco de dados de backup do Repositório de Gerenciamento Central será configurado no pool de backup. A qualquer momento, um dos dois bancos de dados do Repositório de Gerenciamento Central está ativo e o outro está em espera. O conteúdo é replicado pelo Serviço de Backup do banco de dados ativo para aquele em espera.
  
![Mostra dois Pools de Front-End, um com repositório de CMS ativo e o outro com o repositório de CMS de backup passivo](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante um failover de pool que envolve o pool que hospeda o repositório de gerenciamento Central, você deve fazer o failover do repositório de gerenciamento Central antes de você failover de pool Front-End.
  
Depois que o desastre for resolvido, não será necessário fazer failback do Repositório de Gerenciamento Central. Ele poderá permanecer no pool para o qual você fez failover.
  
Os alvos projetados para failover do repositório de gerenciamento Central serão de 5 minutos para objetivo de tempo de recuperação (RTO) e objetivo (RPO) de ponto de 5 minutos para a recuperação.
  
## <a name="front-end-pool-pairing-data-security"></a>Segurança de dados de emparelhamento do Pool de Front-Ends

O Serviço de Backup transfere dados do usuário e conteúdo de conferência entre dois Pools de Front-Ends emparelhados de forma contínua. Os dados do usuário contêm URIs SIP de usuário, bem como programações de conferência, listas de contatos e configurações. O conteúdo de conferência inclui uploads do Microsoft PowerPoint e quadros de comunicações usados em conferências.
  
A partir do pool de origem, esses dados são exportados do armazenamento local, compactados e depois transferidos ao Pool de destino, onde são descompactados e importados para o armazenamento local. O Serviço de Backup pressupõe que o link de comunicações entre os dois data centers está dentro da rede corporativa que está protegida a partir da Internet. Ela não criptografa os dados transferidos entre os dois data centers, nem os dados são originariamente encapsulados dentro de um protocolo protegido, como HTTPS. Portanto, um ataque man-in-the-middle da equipe interna dentro da rede corporativa é possível.
  
Qualquer empresa que implanta Skype para Business Server em vários data centers e usa o recurso de recuperação de desastres deve assegurar que o tráfego entre data centers está protegido pela Intranet da empresa. As empresas que se preocupam com a proteção a ataques internos devem proteger os links de comunicação entre os data centers. Este é um requisito padrão que também ajuda a proteger vários outros tipos de dados confidenciais corporativos que são transferidos entre data centers.
  
Embora exista o risco de ataques de "intrusos" na rede corporativa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados dos usuários expostos pelo Serviço de Backup (como URIs SIP) estão geralmente disponíveis para todos os funcionários da empresa através de outros meios, como o Catálogo de Endereços Global ou outro software de diretório. Portanto, o foco deve estar em proteger a WAN entre os dois data centers quando o Serviço de Backup é usado para copiar dados entre os dois pools emparelhados.
  
### <a name="mitigating-security-risks"></a>Mitigação dos riscos à segurança

Você tem várias formas de melhorar a proteção à segurança do tráfego do Serviço de Backup. Isto abrange desde restringir o acesso aos data centers a proteger o transporte de WAN entre os dois data centers. Na maioria dos casos, as empresas Implantando Skype para Business Server já podem ter a infraestrutura de segurança necessária in-loco. No caso de empresas que buscam orientação, a Microsoft oferece uma solução como um exemplo de como estabelecer uma infraestrutura de TI segura. Para obter detalhes, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544). 
  
Nós não implicam que é a única solução, nem que podemos implicam que é a solução preferida para Skype para Business Server. Recomendamos que os clientes corporativos escolham a solução mais adequada às suas necessidades específicas, com base em sua infraestrutura e requisitos de segurança de TI. A solução exemplo da Microsoft emprega o IPSec e a Política de Grupo para o Isolamento de Servidor e Domínio.
  
Outra solução possível é usar o IPSec apenas para ajudar a proteger os dados enviados pelo próprio Serviço de Backup. Se você escolher este método, deverá configurar as regras do IPSec para o protocolo SMB nos seguintes servidores, onde Pool A e Pool B são dois Pools de Front-Ends emparelhados.
  
- O serviço de SMB (TCP/445) de cada servidor Front-End no Pool A para o repositório de arquivos usado pelo Pool b
    
- O serviço SMB (TCP/445) de cada servidor Front-End no Pool B para o repositório de arquivos usado pelo Pool A.
    
> [!CAUTION]
>  O IPsec não deve ser usado para substituir a segurança no nível de aplicativo, como SSL/TLS. Uma vantagem de usar o IPsec é que ele pode fornecer segurança ao tráfego da rede para os aplicativos existentes sem ter de alterá-los. As empresas que deseja apenas o transporte seguro entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede sobre as maneiras de configurar as conexões WAN seguras usando o equipamento do fornecedor.
  
## <a name="see-also"></a>Consulte também

#### 

[Implantar pools de Front-End pareados para recuperação de desastres em Skype para Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)

