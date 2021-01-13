---
title: Compartilhamento de tela baseado em vídeo do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informações de configuração e planejamento do Skype for Business Server para o VbSS (Compartilhamento de Tela Baseado em Vídeo)
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832761"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Compartilhamento de tela baseado em vídeo do Skype for Business Server 
 
O VbSS (Compartilhamento de Tela Baseado em Vídeo) no Skype for Business Server 2015 agora está disponível para download: [Atualização Cumulativa KB3061064 do Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=47690) O VbSS está incluído no Skype for Business Server 2019.
  
Compartilhamento de tela baseado em vídeo, ou VbSS, saída do Lync compartilhamento de tela. A diferença entre o VbSS e o compartilhamento de tela tradicional tem a ver com os protocolos subjacentes usados e o que eles se destacam. O compartilhamento de tela usa o protocolo de área de trabalho remota (RDP), que é ótimo para criar milhares de sessões de 1 a 1 entre computadores das pessoas. A tecnologia mais nova, o VbSS, usará o Protocolo de Datagrama do Usuário (UDP).
  
O Skype for Business Server queria melhorar o 1-para-1 das pessoas e suas conversas e experiências de reunião entre várias pessoas. O VbSS usa a plataforma de mídia (que depende do UDP como protocolo subjacente), com o objetivo de melhorar os tempos de início do vídeo, a qualidade de exibição do que você está assistindo (especialmente se o que você estiver assistindo estiver se movendo rapidamente) e a confiabilidade geral.
  
Parte da meta de melhorar o compartilhamento de tela é que as transições entre o VbSS e o RDP sejam o mais perfeitas possível quando elas ocorrem. Como o VbSS é uma atualização para a tecnologia subjacente usada no compartilhamento de tela do Skype for Business Server, pode ser difícil detectar qual tecnologia você está utilizando, a menos que você esteja analisando detalhes sip no tráfego de rede ou compartilhando conteúdo que está se movendo rapidamente ou 3D. Se, por exemplo, seu local de trabalho tiver muitos clientes herdado, o RDP ainda estará disponível como um failsafe para suas reuniões e conversas. O Skype for Business Server usa lógica interna para decidir qual dos dois métodos (VbSS ou compartilhamento de tela tradicional) aplicar quando os clientes se conectam. O RDP pode, e será, substituído pelo VbSS quando a situação o chamar, para que sua experiência de exibição não seja interrompida.
  
## <a name="planning"></a>Planejamento

### <a name="vbss-pros-and-cons"></a>Prós e contras do VbSS

Alternar para o VbSS tem como objetivo fazer três melhorias principais:
  
1. Fazer compartilhamento de tela (até 5%) mais confiável em comparação com o RDP sozinho.

2. Acelerar a configuração da sessão e a experiência de vídeo em comparação com o RDP sozinho (configuração na metade do tempo, com uma melhoria de 6:1 em quadros por segundo).

3. Funciona muito melhor do que o RDP em condições de baixa largura de banda, mesmo ao compartilhar conteúdo de alto movimento, como gráficos 3D.
    
Lembre-se de que esses números dependem da saúde e do ajuste de desempenho adequado da sua rede e podem envolver redes externas às suas próprias, se seus clientes estão em dispositivos móveis.
  
Você também deve estar ciente de que alguma fidelidade/precisão do conteúdo compartilhado foi negociada por confiabilidade, velocidade e eficiência. Na maioria dos casos, isso não estará prontamente visível para os usuários.
  
### <a name="ports-and-protocols"></a>Portas e protocolos

**Portas de servidor necessárias**

|**Função de servidor**|**Nome do serviço**|**Intervalo de porta ou porta**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.  <br/> |
|Servidores Front-End  <br/> |Serviço de compartilhamento de aplicativos do Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervalo de porta de mídia usado para compartilhamento de aplicativo.  <br/> |
   
**Portas do cliente necessárias**

|**Componente**|**Intervalo de portas**|**Protocolo**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Compartilhamento de aplicativos  <br/> |
   
Se a QoS estiver habilitada para as seguintes portas de mídia e o VbSS também estiver habilitado, durante uma conferência que inclui o compartilhamento de área de trabalho, a MCU AS usará as configurações de porta de vídeo mostradas em negrito abaixo para o tráfego de compartilhamento de tela. 
  
> [!IMPORTANT]
> Essas configurações são um caso especial, e essas configurações exatas devem ser usadas na implementação desses dois recursos. Isso substitui outras configurações recomendadas na [documentação para QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx). Para o compartilhamento de aplicativos, você também precisará especificar ASMCUSVC.exe no GPO QoS, além de definir esses valores de porta. 
  
**Configurações necessárias de QoS/VbSS do Servidor de Aplicativos**

|**Propriedade**|**Valor da porta**|**Protocolo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Planejamento de capacidade

Cada Servidor Front End que executa a Atualização Cumulativa 2 (CU2) ou posterior do Skype for Business Server 2015 oferece suporte a até 375 participantes para compartilhamento de tela usando RDP (embora apenas 250 por reunião). Essa capacidade não muda após a CU3, quando o VbSS é introduzido e usado.
  
Dito isso, fizemos testes de desempenho e estresse em nosso laboratório, e as medições a seguir também devem ser consideradas em relação à sua própria implantação (dependendo do uso, é claro).
  
Supondo:
  
- Você está usando o Skype for Business Server 2015 CU2 ou posterior em sua implantação.
    
- Todos os usuários em seu ambiente do Skype for Business Server têm resoluções de tela superiores a 1920x1080.
    
Em capacidade total (conforme mencionado acima, são 375 participantes de compartilhamento de tela por Servidor #A0 no total, embora apenas 250 por reunião), seu Servidor #A0 pode estar utilizando cerca de 89% dos 1 Gigabit de placa de rede. Isso porque a tecnologia de compartilhamento de tela existente no Skype for Business Server CU2 (RDP) transmite o conteúdo na tela na resolução nativa do computador do apresentador. Portanto, com resoluções de tela maiores fatoradas, talvez você já esteja enfrentando gargalos de rede para o compartilhamento de tela com o Skype for Business Server 2015 CU2.
  
Para atenuar isso, uma ou mais das seguintes opções podem ser úteis:
  
- Atualize seu Servidor Front End de uma placa de rede de 1 Gigabit para uma placa Ethernet de 10 Gigabit.

- Aumente o número de Servidores front-end para balancear a carga do tráfego.

- Limite a largura de banda (taxa de bits) usada para VbSS e RDP colocando um limite na largura de banda máxima usada por ambos os canais.
    
Os números nesta tabela são influenciados por redes individuais e pelo conteúdo que está sendo compartilhado. Teste para estabelecer linhas de base para sua rede ou redes.
  
|**Conteúdo de 1080p**|**Média de RDP**|**Pico RDP**|**Média do VbSS**|**Pico do VbSS**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Vídeo  <br/> |5mbps  <br/> |7mbps  <br/> |1,3mbps  <br/> |2,2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia

A largura de banda do VbSS é:
  
|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa de bits máxima de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (A taxa de proporção depende da resolução do monitor do sharer e nem sempre será de 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Suporte a clientes e servidores

O compartilhamento de tela baseado em vídeo requer o Skype for Business Server 2015 CU3 ou posterior, e uma versão atual dos clientes de suporte listados na comparação de recursos do cliente móvel para o suporte do [Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [Reuniões.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
Há situações em que o compartilhamento de tela fará a transição para o RDP, como estas:
  
- Se sua conta estiver hospedada em um ambiente em que o ASMCU não atende ao build mínimo que dá suporte ao VbSS.
- Se alguém que usa uma versão mais antiga do cliente Skype for Business ingressar em sua sessão, por exemplo, qualquer pessoa que use qualquer versão de cliente do Windows menor que 16.0.6330.1000, Dispositivos do Sistema de Sala do Skype for Business ou Aplicativos Móveis do Skype for Business. 
- Se um usuário estiver compartilhando do Skype for Business Web App.
- Se alguém estiver usando o Skype for Business no Mac e não estiver no Skype for Business Online ou no Skype for Business Server 2015 com a atualização cumulativa de julho de 2018 (ou posterior).
- Se alguém iniciar qualquer programa/compartilhamento do Windows.
- Se alguém começar a gravar a sessão.
- Se alguém invocar o Controle de Tela Remota durante a sessão. 
- Reuniões com mais de 250 participantes (nas quais o VbSS não é suportado no momento).

Esteja ciente de que, depois que a sessão transitar para RDP, ela não fará a transição de volta para o VbSS. Novamente, a transição do VbSS deve ser perfeita e, com certeza, não será fácil de detectar na maioria das situações.
    
> [!NOTE]
> Não há suporte para bloquear ou tentar bloquear a transição do VbSS para o RDP no compartilhamento de tela do Skype for Business. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Habilitando, desabilitando e configurando o VbSS

O melhor é que, depois de instalar a Atualização Cumulativa 3 (CU3) ou posterior do Skype for Business Server 2015, todos os usuários serão habilitados para VbSS 1 para 1 e vários participantes por padrão. Isso poderá ser problemático se você tiver um motivo para não habilitar essa funcionalidade para todos os seus usuários. Nesse caso, você poderá usar estas etapas para desabilitar os usuários (as etapas de habilitar usuários seguirão):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Como desabilitar o uso do VbSS pelos usuários

- Você pode atribuir uma política de usuário que não permita o VbSS a qualquer usuário que não deva usar o VbSS executando esse cmdlet no Console de Gerenciamento do Skype for Business (substitua [PolicyName] pela política para a que você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar desativar o VbSS completamente, execute este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Para obter mais informações sobre esse comando, [consulte Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião com vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política do organizador da reunião. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Como permitir que os usuários usem o VbSS

- Você pode atribuir uma política de usuário específica que permita o VbSS a qualquer usuário que precise usar o VbSS executando esse cmdlet no Console de Gerenciamento do Skype for Business (substitua [PolicyName] pela política para a que você está fazendo isso):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Você também pode atualizar a política de conferência global, que afetará todos os usuários sem uma política atribuída:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Para obter mais informações sobre esse comando, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Se você precisar ativar o VbSS novamente depois de a desativar (ele está a partir do padrão), execute este comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Para obter mais informações sobre esse comando, [consulte Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Em uma reunião com vários participantes do Skype for Business, todos os pontos de extremidade do cliente respeitarão a configuração de política do organizador da reunião. 
  
## <a name="see-also"></a>Confira também

[Atualização cumulativa KB3061064 do Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=47690)
  
[O VBSS (compartilhamento de tela baseado em vídeo) está disponível no Skype for Business Server 2015](https://support.microsoft.com/kb/3170163)
