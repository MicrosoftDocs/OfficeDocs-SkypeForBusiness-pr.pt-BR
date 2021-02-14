---
title: Recuperação de desastre do pool de front-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Para recuperação de desastres, o Skype for Business Server oferece emparelhamento de pool com failover caso um pool falhe.
ms.openlocfilehash: d77a0d56c7a3e3d80c6e735fd6eff178606f667a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802911"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Recuperação de desastre do pool de front-end no Skype for Business Server
 
Para recuperação de desastres, o Skype for Business Server oferece emparelhamento de pool com failover caso um pool falhe.
  
Para as opções de recuperação de desastre mais robustas no Skype for Business Server, implante pares de pools de Front-End em dois sites geograficamente dispersos. Cada site tem um pool de Front-End que é emparelhado com um pool de Front-End correspondente no outro site. Ambos os sites estão ativos, e o Serviço de Backup fornece replicação de dados em tempo real para manter os pools sincronizados. Consulte [Implantar pools de front-end emparelhados](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) para recuperação de desastre no Skype for Business Server se quiser implementar o emparelhamento de pool de Front-End.
  
![Mostra pools de front-end em dois sites diferentes, emparelhados entre si](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Se o pool em um site falhar, você poderá fazer fail over dos usuários desse pool para o pool no outro site, que atende a todos os usuários em ambos os pools. Para planejamento de capacidade, você deve projetar cada pool para ser capaz de lidar com a carga de trabalho de todos os usuários em ambos os pools em caso de desastre.
  
Dois data centers que incluem pools de Front End emparelhados entre si podem estar a qualquer distância. Recomendamos que você emparelhe dois data centers na mesma região do mundo, com links de alta velocidade entre eles. 
  
Ter dois data centers em regiões do mundo é possível, mas pode incorrer em maior perda de dados se houver um desastre, devido à latência na replicação de dados.
  
Ao planejar quais pools emparelhar, você deve ter em mente que apenas os seguintes emparelhamentos são suportados:
  
- Pools do Enterprise Edition só podem ser emparelhados com outros pools do Enterprise Edition. Da mesma forma, pools do Standard Edition podem ser emparelhados somente com outros pools do Standard Edition.
    
- Pools físicos só podem ser emparelhados com outros pools físicos. Da mesma forma, pools virtuais só podem ser emparelhados com outros pools virtuais.
    
- Os pools emparelhados devem estar executando o mesmo sistema operacional base.
    
Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas. Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool do Enterprise Edition com um pool do Standard Edition. No entanto, esses tipos de emparelhamento não são suportados.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relacionamentos de Registrador de Backup e Aparelhos de FilialVivível

Além de oferecer capacidade para recuperação de desastre, dois pools pareados servem como backup de Registrars. Cada pool pode ser o backup de apenas um outro pool de Front-End.
  
Embora as relações de backup entre dois pools de Front-End deverão ser 1:1 e simétricas, cada pool de Front End ainda poderá ser o registrador de backup para qualquer número de Aparelhos de FilialVivíveis.
  
Observe que o Skype for Business não estende o suporte à recuperação de desastre para usuários que estão em um Aparelho de FilialVivível. Se um pool de Front-End que serve como backup para um Aparelho de Filial Survivível ficar inocável, os usuários que entraram no Aparelho de Filial Sobrevivência entrarão no modo de resiliência, mesmo que os usuários que estão no pool de Front-End sejam baixados para o pool de Front-End de backup.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tempo de recuperação para failover de pool e failback de pool

Para failover de pool e failback de pool, o destino de engenharia para objetivo de tempo de recuperação (RTO) é de 15 a 20 minutos. Esse é o tempo necessário para que o failover aconteça, depois que os administradores determinarem que houve um desastre e iniciar os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomar uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.
  
Para failover de pool e failback de pool, o destino de engenharia para objetivo de ponto de recuperação (RPO) é de 5 minutos. Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup. Por exemplo, se um pool cair às 10:00 e o RPO for de 5 minutos, os dados gravados no pool entre 09:55 e 10:00 A.M.pode não ter replicado para o pool de backup e seria perdido.
  
Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região com alta velocidade e trasporte de baixa latência entre os dois locais. Esses números são medidos para um pool com 40.000 usuários ativos ao mesmo tempo e 200.000 usuários habilitados para o Skype for Business em relação a um modelo de usuário pré-definido onde não há backlog na replicação de dados. Eles estão sujeitos à alteração baseado no teste e validação de desempenho.
  
## <a name="central-management-store-failover"></a>Failover do armazenamento de Gerenciamento Central

O armazenamento de Gerenciamento Central contém dados de configuração sobre os servidores e serviços em sua implantação. Cada implantação do Skype for Business Server inclui um armazenamento de Gerenciamento Central, que é hospedado pelo Servidor back-end de um pool de Front-End.
  
Se você emparelhar o pool que hospeda o armazenamento de Gerenciamento Central, um banco de dados de backup do Armazenamento Central será definido no pool de backup. A qualquer momento, um dos dois bancos de dados do Armazenamento Central está ativo e o outro está em espera. O conteúdo é replicado pelo Serviço de Backup do banco de dados ativo para o modo de espera.
  
![Mostra dois Pools de Front-End, um com o armazenamento CMS ativo e outro com o armazenamento de CMS de backup passivo](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante um failover de pool que envolve o pool que hospeda o armazenamento de Gerenciamento Central, você deve fazer failover do armazenamento de Gerenciamento Central antes de fazer failover do pool de Front-End.
  
Após a reparação do desastre, não é necessário fazer fail back do armazenamento de Gerenciamento Central. O armazenamento de Gerenciamento Central pode permanecer no pool em que você fez o failed over.
  
As metas de engenharia para failover do armazenamento de Gerenciamento Central são 5 minutos para objetivo de tempo de recuperação (RTO) e 5 minutos para objetivo de ponto de recuperação (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Segurança de dados de emparelhamento do pool de front-end

O Serviço de Backup transfere dados do usuário e conteúdo de conferência entre dois pools de Front-End emparelhados continuamente. Os dados do usuário contêm URIs SIP do usuário, bem como agendamentos de conferências, listas de contatos e configurações. O conteúdo da conferência inclui carregamentos do Microsoft PowerPoint, bem como whiteboards usados em conferências.
  
A partir do pool de origem, esses dados são exportados do armazenamento local, recortados e transferidos para o Pool de destino, onde são descortados e importados para o armazenamento local. O Serviço de Backup pressupõe que o link de comunicação entre os dois data centers está dentro da rede da empresa, protegida da Internet. Ele não criptografa os dados transferidos entre os dois data centers, nem os dados são encapsulados de forma nativa em um protocolo seguro, como HTTPS. Portanto, é possível um ataque man-in-the-middle de funcionários internos dentro da rede corporativa.
  
Qualquer empresa que implanta o Skype for Business Server em vários data centers e usa o recurso de recuperação de desastres deve garantir que o tráfego entre data centers seja protegido por sua Intranet corporativa. As empresas que se preocupam com a proteção contra ataques internos devem proteger os links de comunicação entre os data centers. Esse é um requisito padrão que também ajuda a fazer a tecnologia de vários outros tipos de dados confidenciais corporativos transferidos entre data centers.
  
Embora exista o risco de ataques de "intrusos" na rede da empresa, ele é relativamente limitado em comparação a expor o tráfego à Internet. Especificamente, os dados do usuário expostos pelo Serviço de Backup (como URIs SIP) geralmente estão disponíveis para todos os funcionários da empresa por outros meios, como o Livro de Endereços Global ou outro software de diretório. Portanto, seu foco deve estar em proteger a WAN entre os dois data centers quando o Serviço de Backup for usado para copiar dados entre os dois pools emparelhados.
  
### <a name="mitigating-security-risks"></a>Mitigando os riscos de segurança

Você tem várias maneiras de aprimorar a proteção de segurança para o tráfego do Serviço de Backup. Isso vai desde restringir o acesso aos data centers até proteger o transporte wan entre os dois data centers. Na maioria dos casos, as empresas que implantam o Skype for Business Server podem já ter a infraestrutura de segurança necessária. Para empresas que procuram orientação, a Microsoft fornece uma solução como um exemplo de como criar uma infraestrutura de TI segura. Para obter detalhes, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544) . 
  
Não implicamos que esta é a única solução, nem implicamos que ela é a solução preferida para o Skype for Business Server. Recomendamos que os clientes corporativos escolham a solução adequada às suas necessidades específicas, com base em sua infraestrutura e requisitos de segurança de TI. A solução da Microsoft de exemplo emprega IPSec e Política de Grupo para Isolamento de Servidor e Domínio.
  
Outra solução possível é usar IPSec apenas para ajudar a proteger os dados enviados pelo próprio Serviço de Backup. Se você escolher esse método, deverá configurar as regras IPSec para o protocolo SMB para os seguintes servidores, onde Pool A e Pool B são dois pools de Front-End emparelhados.
  
- O serviço SMB (TCP/445) de cada Servidor Front End no Pool A para o Armazenamento de Arquivos usado pelo Pool B.
    
- O Serviço SMB (TCP/445) de cada Servidor Front End no Pool B até o Armazenamento de Arquivos usado pelo Pool A.
    
> [!CAUTION]
>  O IPsec não se destina a substituir a segurança no nível do aplicativo, como SSL/TLS. Uma vantagem de usar o IPsec é que ele pode fornecer segurança de tráfego de rede para aplicativos existentes sem precisar alterá-los. As empresas que querem apenas proteger o transporte entre os dois data centers devem consultar seus respectivos fornecedores de hardware de rede sobre maneiras de configurar conexões WAN seguras usando o equipamento do fornecedor.
  
## <a name="see-also"></a>Confira também

[Implantar pools de front-end emparelhados para recuperação de desastre no Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
