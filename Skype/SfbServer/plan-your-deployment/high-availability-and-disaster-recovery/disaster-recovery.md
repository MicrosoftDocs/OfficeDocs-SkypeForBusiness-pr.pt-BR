---
title: Recuperação de desastre de pool de front-end no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Para recuperação de desastres, Skype for Business Server oferece emparelhamento de pool com failover no caso de um pool cair.
ms.openlocfilehash: 0c36f4b1fdb243284453cb61e30879f95fdd4fa3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401755"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Recuperação de desastre de pool de front-end no Skype for Business Server
 
Para recuperação de desastres, Skype for Business Server oferece emparelhamento de pool com failover no caso de um pool cair.
  
Para as opções de recuperação de desastres mais robustas Skype for Business Server, implante pares de pools de Front-End em dois sites geograficamente dispersos. Cada site tem um pool de Front-End que é emparelhado com um pool de Front-End correspondente no outro site. Ambos os sites estão ativos e o Serviço de Backup fornece replicação de dados em tempo real para manter os pools sincronizados. Consulte [Deploy paired Front End pools for disaster recovery in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) if you want to implement Front End pool pairing.
  
![Mostra Pools de Front-End em dois sites diferentes, emparelhados uns com os outros.](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Se o pool em um site falhar, você poderá fazer fail over dos usuários desse pool para o pool no outro site, que atende a todos os usuários em ambos os pools. Para o planejamento de capacidade, você deve projetar cada pool para poder lidar com a carga de trabalho de todos os usuários em ambos os pools em caso de desastre.
  
Dois data centers que incluem pools de Front-End emparelhados entre si podem estar a qualquer distância. Recomendamos que você emparelhe dois data centers na mesma região do mundo, com links de alta velocidade entre eles. 
  
Ter dois data centers em todas as regiões do mundo é possível, mas pode incorrer em perda de dados mais alta se houver um desastre, devido à latência na replicação de dados.
  
Ao planejar quais pools emparelhar, você deve ter em mente que apenas os seguintes emparelhamentos são suportados:
  
- Pools do Enterprise Edition só podem ser emparelhados com outros pools do Enterprise Edition. Da mesma forma, pools do Standard Edition podem ser emparelhados somente com outros pools do Standard Edition.
    
- Pools físicos só podem ser emparelhados com outros pools físicos. Da mesma forma, pools virtuais só podem ser emparelhados com outros pools virtuais.
    
- Os pools emparelhados devem estar executando o mesmo sistema operacional base.
    
Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas. Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool do Enterprise Edition com um pool do Standard Edition. No entanto, esses tipos de emparelhamentos não são suportados.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relações de Registrador de Backup e Aparelhos de Filial Desaviváveis

Além de oferecer capacidade para recuperação de desastre, dois pools pareados servem como backup de Registrars. Cada pool pode ser o backup de apenas um outro pool de Front-End.
  
Mesmo que as relações de backup entre dois pools de Front-End sejam 1:1 e simétricas, cada pool de Front-End ainda pode ser o registrador de backup para qualquer número de Aparelhos de Filial Desavisados.
  
Observe que Skype for Business não estende o suporte à recuperação de desastres aos usuários que estão em um Aparelho de Filial Desavivável. Se um pool de Front-End que serve como backup para um Aparelho de Filial Desavivável for baixado, os usuários que entraram no Aparelho de Filial Desavivável entrarão no modo de resiliência, mesmo que os usuários no pool de Front-End sejam reprovados no pool de Front-End de backup.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tempo de recuperação para failover de pool e failback de pool

Para failover de pool e failback de pool, o objetivo de engenharia para o objetivo de tempo de recuperação (RTO) é de 15 a 20 minutos. Esse é o tempo necessário para que o failover aconteça, depois que os administradores determinarem que houve um desastre e iniciarem os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomar uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.
  
Para failover de pool e failback de pool, o objetivo de engenharia para o objetivo de ponto de recuperação (RPO) é de 5 minutos. Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup. Por exemplo, se um pool cair às 10:00 e o RPO for de 5 minutos, os dados gravados no pool entre 9:55. e 10:00 .M .talvez não tenham replicado para o pool de backup e seriam perdidos.
  
Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região com alta velocidade e trasporte de baixa latência entre os dois locais. Esses números são medidos para um pool com 40.000 usuários simultâneos ativos e 200.000 usuários habilitados para Skype for Business em relação a um modelo de usuário pré-definido onde não há backlog na replicação de dados. Eles estão sujeitos à alteração baseado no teste e validação de desempenho.
  
## <a name="central-management-store-failover"></a>Failover do armazenamento de Gerenciamento Central

O armazenamento de Gerenciamento Central contém dados de configuração sobre os servidores e serviços em sua implantação. Cada Skype for Business Server de implantação inclui um armazenamento de Gerenciamento Central, que é hospedado pelo Servidor Back-End de um pool de Front-End.
  
Se você emparelhar o pool que hospeda o armazenamento de Gerenciamento Central, um banco de dados do armazenamento de Gerenciamento Central de backup será definido no pool de backup. A qualquer momento, um dos dois bancos de dados do Armazenamento de Gerenciamento Central está ativo e o outro é um modo de espera. O conteúdo é replicado pelo Serviço de Backup do banco de dados ativo para o modo de espera.
  
![Mostra dois Pools front-end, um com o armazenamento CMS ativo e o outro com o armazenamento CMS de backup passivo.](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante um failover de pool que envolve o pool que hospeda o armazenamento de Gerenciamento Central, você deve falhar no armazenamento de Gerenciamento Central antes de falhar no pool de Front-End.
  
Depois que o desastre é reparado, não é necessário fazer o fail back do armazenamento de Gerenciamento Central. O armazenamento de Gerenciamento Central pode permanecer no pool em que você falhou.
  
As metas de engenharia para o failover do armazenamento de Gerenciamento Central são 5 minutos para objetivo de tempo de recuperação (RTO) e 5 minutos para objetivo de ponto de recuperação (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Segurança de dados de emparelhamento de pool de front-end

O Serviço de Backup transfere dados do usuário e conteúdo de conferência entre dois pools front-end emparelhados continuamente. Os dados do usuário contêm URIs SIP do usuário, bem como agendamentos de conferência, listas de contatos e configurações. O conteúdo da conferência inclui PowerPoint carregamentos da Microsoft, bem como os whiteboards usados em conferências.
  
No pool de origem, esses dados são exportados do armazenamento local, recortados e transferidos para o Pool de destino, onde são desacortados e importados para o armazenamento local. O Serviço de Backup pressupõe que o link de comunicação entre os dois data centers está dentro da rede da empresa, protegida da Internet. Ele não criptografa os dados transferidos entre os dois data centers, nem os dados encapsulados de forma nativa em um protocolo seguro, como HTTPS. Portanto, é possível um ataque man-in-the-middle de funcionários internos dentro da rede corporativa.
  
Qualquer empresa que implanta Skype for Business Server em vários data centers e usa o recurso de recuperação de desastres deve garantir que o tráfego entre data centers seja protegido por sua Intranet corporativa. As empresas que se preocupam com a proteção de ataques internos devem proteger os links de comunicação entre os data centers. Esse é um requisito padrão que também ajuda a protech muitos outros tipos de dados confidenciais corporativos transferidos entre data centers.
  
Embora exista o risco de ataques de "intrusos" na rede da empresa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados do usuário expostos pelo Serviço de Backup (como URIs SIP) geralmente estão disponíveis para todos os funcionários da empresa por meio de outros meios, como o Livro de Endereços Global ou outro software de diretório. Portanto, seu foco deve estar em proteger a WAN entre os dois data centers quando o Serviço de Backup for usado para copiar dados entre os dois pools emparelhados.
  
### <a name="mitigating-security-risks"></a>Mitigando riscos de segurança

Você tem muitas maneiras de aprimorar a proteção de segurança para o tráfego do Serviço de Backup. Isso varia de restringir o acesso aos data centers até proteger o transporte wan entre os dois data centers. Na maioria dos casos, as empresas que implantam Skype for Business Server podem já ter a infraestrutura de segurança necessária. Para empresas que procuram orientação, a Microsoft fornece uma solução como um exemplo de como criar uma infraestrutura de TI segura. Para obter detalhes, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)). 
  
Não sugerimos que ela seja a única solução, nem sugerimos que ela seja a solução preferencial para Skype for Business Server. Recomendamos que os clientes corporativos escolham a solução de acordo com suas necessidades específicas, com base em sua infraestrutura e requisitos de segurança de TI. O exemplo de solução da Microsoft emprega IPSec e Política de Grupo para Isolamento de Servidor e Domínio.
  
Outra solução possível é usar IPSec apenas para ajudar a proteger os dados enviados pelo próprio Serviço de Backup. Se você escolher esse método, configure as regras IPSec para o protocolo SMB para os seguintes servidores, onde Pool A e Pool B são dois pools front-end emparelhados.
  
- O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool A até o Armazenamento de Arquivos usado pelo Pool B.
    
- O Serviço SMB (TCP/445) de cada Servidor Front-End no Pool B até o Armazenamento de Arquivos usado pelo Pool A.
    
> [!CAUTION]
>  O IPsec não se destina a substituir a segurança no nível do aplicativo, como SSL/TLS. Uma vantagem de usar o IPsec é que ele pode fornecer segurança de tráfego de rede para aplicativos existentes sem precisar alterá-los. As empresas que querem apenas proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede sobre maneiras de configurar conexões WAN seguras usando o equipamento do fornecedor.
  
## <a name="see-also"></a>Confira também

[Implantar pools front-end emparelhados para recuperação de desastres Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)