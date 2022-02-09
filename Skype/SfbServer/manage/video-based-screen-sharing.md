---
title: Compartilhamento de tela baseado em vídeo do Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server de planejamento e configuração para vbSS (compartilhamento de tela baseado em vídeo)
ms.openlocfilehash: 0eb381504e797879d9e4235d7ae9cce69f1a468c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396423"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Compartilhamento de tela baseado em vídeo do Skype for Business Server 
 
O VbSS (Compartilhamento de Tela baseado em vídeo) no Skype For Business Server 2015 agora está disponível para download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). O VbSS está incluído no Skype for Business Server 2019.
  
O Compartilhamento de Tela baseado em vídeo, ou VbSS, cresceu a partir do Lync screen-sharing. A diferença entre o VbSS e o compartilhamento de tela tradicional tem a ver com os protocolos subjacentes usados e o que eles se destacam. O compartilhamento de tela usa o protocolo de área de trabalho remota (RDP), que é ótimo na criação de milhares de sessões de 1 a 1 entre os computadores das pessoas. A tecnologia mais nova, VbSS, usará o Protocolo de Datagrama do Usuário (UDP).
  
Skype for Business Server queria melhorar as experiências de reunião e conversas de 1 a 1 das pessoas. O VbSS usa a plataforma de mídia (que depende do UDP como o protocolo subjacente), com o objetivo de melhorar os tempos de início do vídeo, a qualidade de exibição do que você está assistindo (especialmente se o que você está assistindo está se movendo rapidamente) e a confiabilidade geral.
  
Parte do objetivo de melhorar o compartilhamento de tela é que as transições entre VbSS e RDP sejam o mais perfeitas possível quando elas ocorrem. Como o VbSS é uma atualização para a tecnologia subjacente usada no compartilhamento de tela para o Skype for Business Server, pode ser difícil detectar qual tecnologia você está aproveitando, a menos que você esteja analisando detalhes SIP no tráfego de rede ou compartilhando conteúdo que está se movendo rapidamente ou 3D. Se, por exemplo, seu local de trabalho tiver muitos clientes herdado, o RDP ainda estará disponível como um failsafe para suas reuniões e conversas. Skype for Business Server lógica interna para decidir quais dos dois métodos (VbSS ou compartilhamento de tela tradicional) serão aplicados quando os clientes se conectarem. O RDP pode e será substituído pelo VbSS quando a situação o chamar, para que sua experiência de exibição não seja interrompida.
  
## <a name="planning"></a>Planejamento

### <a name="vbss-pros-and-cons"></a>Prós e contras do VbSS

Alternar para o VbSS tem como objetivo fazer três melhorias principais:
  
1. Tornar o compartilhamento de tela (até 5%) mais confiável em comparação com o RDP sozinho.

2. Tornar a configuração da sessão e a experiência de vídeo mais rápidas em comparação com o RDP (configuração na metade do tempo, com uma melhoria de 6:1 em quadros por segundo).

3. Funciona muito melhor que o RDP em condições de baixa largura de banda, mesmo ao compartilhar conteúdo de alto movimento, como gráficos 3D.
    
Lembre-se de que esses números dependem da saúde e do ajuste adequado do desempenho da sua rede e podem envolver redes externas às suas próprias, se seus clientes estão em dispositivos móveis.
  
Você também deve estar ciente de que alguma fidelidade/nitidez do seu conteúdo compartilhado foi negociada por confiabilidade, velocidade e eficiência. Na maioria dos casos, isso não será facilmente visível para os usuários.
  
### <a name="ports-and-protocols"></a>Portas e protocolos

**Portas de servidor necessárias**

|**Função de servidor**|**Nome do serviço**|**Intervalo de porta ou porta**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Skype for Business Server serviço de Compartilhamento de Aplicativos  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Skype for Business Server serviço de Compartilhamento de Aplicativos  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
   
**Portas de cliente necessárias**

|**Componente**|**Intervalo de portas**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Compartilhamento de aplicativos  <br/> |
   
Se a QoS estiver habilitada para as seguintes portas de mídia e o VbSS também estiver habilitado, durante uma conferência que inclui o compartilhamento de área de trabalho, o AS MCU usará as configurações de porta de vídeo mostradas em negrito abaixo para o tráfego de compartilhamento de tela. 
  
> [!IMPORTANT]
> Essas configurações são um caso especial, e essas configurações exatas devem ser usadas ao implementar ambos os recursos. Isso substitui outras configurações recomendadas na [documentação para QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos). Para o compartilhamento de aplicativos, você também precisará especificar ASMCUSVC.exe no GPO QoS, além de definir esses valores de porta. 
  
**Configurações necessárias do QoS/VbSS do Application Server**

|**Propriedade**|**Valor da porta**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planejamento de capacidade

Cada Servidor Front-End que executa Skype for Business Server Atualização Cumulativa 2 (CU2) 2015 ou posterior oferece suporte a até 375 participantes para compartilhamento de tela usando RDP (embora apenas 250 por reunião). Essa capacidade não muda após a CU3, quando o VbSS é introduzido e usado.
  
Dito isso, fizemos testes de desempenho e estresse em nosso laboratório e as medidas a seguir também devem ser consideradas em relação à sua própria implantação (dependendo do uso, é claro).
  
Supondo:
  
- Você está usando o Skype for Business Server 2015 CU2 ou posterior em sua implantação.
    
- Todos os usuários em seu ambiente Skype for Business Server têm resoluções de tela superiores a 1920x1080.
    
Com capacidade total (que, conforme mencionado acima, é de 375 participantes de compartilhamento de tela por Servidor #A0 no total, embora apenas 250 por reunião), seu Servidor #A0 pode estar utilizando ~89% do 1 Gigabit de cartão de rede. Isso porque a tecnologia de compartilhamento de tela existente no Skype for Business Server CU2 (RDP) transmite o conteúdo na tela na resolução nativa do computador do apresentador. Portanto, com resoluções de tela mais altas fatoradas, você já pode estar enfrentando gargalos de rede para compartilhamento de tela com Skype for Business Server 2015 CU2.
  
Para atenuar isso, uma ou mais das seguintes opções podem ser úteis:
  
- Atualize seu Servidor Front-End de uma placa de rede de 1 Gigabit para um cartão Ethernet de 10 Gigabit.

- Aumente o número de Servidores Front-End para balancear o tráfego de carga.

- Limite a largura de banda (bitrate) usada para VbSS e RDP colocando um limite na largura de banda máxima usada por ambos os canais.
    
Os números nesta tabela são influenciados por redes individuais e pelo conteúdo que está sendo compartilhado. Teste para estabelecer linhas de base para sua rede ou redes.
  
|**Conteúdo 1080p**|**Média de RDP**|**Pico RDP**|**Média do VbSS**|**Pico do VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12 mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5 mbps  <br/> |7mbps  <br/> |1,3mbps  <br/> |2,2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia

A largura de banda do VbSS é:
  
|**Codec de vídeo**|**Resolução e proporção**|**Taxa máxima de bits de carga de vídeo (Kbps)**|**Taxa mínima de bits de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (A taxa de proporção depende da resolução do monitor do sharer e nem sempre será 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Suporte a clientes e servidores

O Compartilhamento de Tela baseado em vídeo requer Skype for Business Server 2015 CU3 ou posterior, e uma versão atual dos clientes de suporte listados na comparação [](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) de recursos do cliente móvel para suporte Skype for Business e [Reuniões](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing). 
  
Há situações em que o compartilhamento de tela fará a transição para o RDP, como estas:
  
- Se sua conta estiver hospedada em um ambiente em que o ASMCU não atende ao build mínimo que dá suporte ao VbSS.
- Se alguém que usa uma versão mais antiga do cliente Skype for Business ingressar em sua sessão, por exemplo, qualquer pessoa que use qualquer versão do cliente Windows que seja inferior a 16.0.6330.1000, dispositivos de sistema de sala Skype for Business ou Skype for Business aplicativos móveis. 
- Se um usuário estiver compartilhando do Skype for Business Web App.
- Se alguém estiver usando Skype for Business no Mac e não estiver no Skype for Business Online ou Skype for Business Server 2015 com a atualização cumulativa de julho de 2018 (ou posterior).
- Se alguém iniciar qualquer Programa/Windows Compartilhamento.
- Se alguém começar a gravar a sessão.
- Se alguém invocar o Controle de Tela Remota durante a sessão. 
- Reuniões com mais de 250 participantes (onde o VbSS não tem suporte no momento).

Esteja ciente de que, uma vez que a sessão transições para RDP, ela não fará a transição de volta para o VbSS. Novamente, a transição do VbSS deve ser perfeita e, com a esperança, não será fácil de detectar na maioria das situações.
    
> [!NOTE]
> Não há suporte para bloquear ou tentar bloquear a transição do VbSS para o RDP Skype for Business compartilhamento de tela. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitando, desabilitando e configurando o VbSS

O ótimo é que, depois de instalar a Atualização Cumulativa 3 (CU3) do Skype for Business Server 2015 ou posterior, todos os usuários serão habilitados para VbSS de 1 a 1 e de várias partes por padrão. Isso pode ser problemático para você se você tiver um motivo para não ter essa funcionalidade habilitada para todos os seus usuários. Nesse caso, você pode usar essas etapas para desabilitar os usuários (as etapas de habilitar usuários seguirão):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Como desabilitar os usuários do uso do VbSS

- Você pode atribuir uma política de usuário que não permita o VbSS a usuários que não devem usar o VbSS executando esse cmdlet no Console de Gerenciamento do Skype for Business (substitua [PolicyName] pela política pela que você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obter mais informações sobre este comando, consulte [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se precisar desativar completamente o VbSS, execute este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obter mais informações sobre este comando, consulte [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de Skype for Business de várias partes, todos os pontos de extremidade do cliente respeitarão a configuração de política do organizador da reunião. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Como permitir que os usuários usem o VbSS

- Você pode atribuir uma política de usuário específica que permita o VbSS a qualquer usuário que precise usar o VbSS executando esse cmdlet no Console de Gerenciamento do Skype for Business (substitua [PolicyName] pela política para a que você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obter mais informações sobre este comando, consulte [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar ativar novamente o VbSS depois de a desativar (ele está on por padrão), você pode executar este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obter mais informações sobre este comando, consulte [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião de vários Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política do organizador da reunião. 
  
## <a name="see-also"></a>Confira também

[Skype for Business Server atualização cumulativa 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[O VBSS (compartilhamento de tela baseado em vídeo) está disponível no Skype for Business Server 2015](https://support.microsoft.com/kb/3170163)