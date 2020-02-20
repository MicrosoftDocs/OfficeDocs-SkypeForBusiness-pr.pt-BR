---
title: Notas de versão
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Este artigo discute melhorias cumulativas nas salas do Microsoft Teams.
ms.openlocfilehash: fc83efc2b3b72be532d29b2698370c655a1da9ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155083"
---
# <a name="release-notes"></a>Notas de versão

Este artigo discute melhorias cumulativas nas salas do Microsoft Teams.

## <a name="version-history"></a>Histórico de versões

|Liberação |Publicado em <br/> Microsoft Store |
|--- |--- |
|4.3.33.0 |1/10/2020 |
|4.3.23.0 |12/13/2019 |
|4.2.4.0 |10/07/2019 |
|4.1.22.0 |08/15/2019 |
|4.0.105.0 |07/10/2019 |
|4.0.85.0 |04/08/2019 |
|4.0.78.0 |03/14/2019 |
|4.0.76.0 |03/04/2019 |
|4.0.64.0 |12/14/2018 |
|4.0.51.0 |11/17/2018 |
|4.0.31.0 |10/16/2018 |
|4.0.27.0 |10/1/2018 |
|4.0.19.0 |08/31/2018 |
|4.0.18.0 |08/27/2018 |
|4.0.8.0 |07/06/2018 |
|3.1.115.0|06/18/2018 |
|3.1.113.0|06/13/2018 |
|3.1.112.0|06/05/2018 |
|3.1.104.0|04/16/2018 |
|3.1.100.0|03/16/2018 |
|3.1.99.0 |3/14/2018 |
|3.1.98.0 |3/8/2018 |
|3.0.16.0 |11/27/2017 |
|3.0.15.0 |10/3/2017 |
|3.0.12.0 |9/1/2017 |
|3.0.8.0 |11/16/2017 |
|3.0.6.0 |11/16/2017 |
|2.0.2.0 |03/15/2017 |
|RTM (1.0.8) |12/7/2016 |

## <a name="microsoft-teams-rooms-feature-introduction-and-issue-resolution"></a>Introdução ao recurso salas do Microsoft Teams e resolução de problemas

### <a name="43330-1102020"></a>4.3.33.0 (1/10/2020)

Apresentado nesta atualização:

- Uma correção de um problema de dimensionamento/oscilação de janela visto em determinadas configurações
- Processamento de calendário para reuniões de terceiros removido
- Configuração de status da Cortana removida

### <a name="43230-12132019"></a>4.3.23.0 (12/13/2019)

Apresentado nesta atualização:

- Atender automaticamente chamadas baseadas em proximidade e configurações de administrador para controlar isso
- Atualização da interface do usuário das configurações do administrador do dispositivo com adição de configuração de dispositivo na guia sobre
- Controle da sala de volta para a tela principal
- SKU da sala de reunião disponível no GCC
- Suporte à câmera de conteúdo para sistema baseado em Surface pro (compilação mínima necessária do aplicativo: 4.2.4.0)

### <a name="4240-10072019"></a>4.2.4.0 (10/07/2019)

Apresentado nesta atualização:

- Suporte do Windows 10 1903. A atualização do Windows 10 1903 é oferecida dentro de alguns dias após a atualização do aplicativo
- Correções para o teclado virtual não são exibidos de forma confiável

### <a name="41220-08152019"></a>4.1.22.0 (08/15/2019)

Apresentado nesta atualização:

- Um novo recurso de câmera de conteúdo que permite que os usuários incluam de forma inteligente um quadro de comunicações tradicional em suas reuniões de equipe
- Melhorias adicionais na interface do usuário do console para reduzir a desordem e as configurações migradas para uma nova barra lateral que é acessada por mais no console
- Botão Desabilitar compartilhamento de bandeja se o cabo de conteúdo local não estiver conectado ou se não houver uma câmera de conteúdo conectada
- Correção de um problema com o teclado virtual em que ele falhou aparece na primeira vez apenas após uma reinicialização do sistema do MTR
- Correções de qualidade e confiabilidade

### <a name="401050-07102019"></a>4.0.105.0 (07/10/2019)

Apresentado nesta atualização:

- Remarcando aplicativos da loja do sistema da sala Skype para "salas do Microsoft Teams"
- Interface do usuário do console de salas do Microsoft Teams realinhada ao Microsoft Teams
- Atualização de tema: manter a imagem de tela de fundo personalizada somente na frente das exibições de sala, enquanto torna a tela de fundo do console uma cor neutra para garantir que os controles da interface do usuário do console atendam às
- Barra universal para controles de chamada em reunião para chamadas de equipe/reuniões para oferecer uma experiência consistente com o Microsoft Teams PC/Web/móvel clientes<sup>1</sup>
- Classificação de comentários de qualidade da chamada após chamadas/reuniões do teams<sup>1</sup>
- Receber/renderizar o Microsoft whiteboard em salas do Microsoft Teams no início da exibição da sala quando compartilhadas do cliente das equipes do PC/Web/celular<sup>1</sup> <sup>2</sup>
- Foi removido o suporte para atualizações do Windows 10 versão 1809 devido a problemas de compatibilidade com o cliente de salas do Microsoft Teams. O suporte do Windows 10 versão 19H1 será adicionado em lançamentos futuros

<sup>1</sup> distribuição de serviço do Microsoft Teams usando anéis do teams. Esse recurso pode estar disponível antes ou depois da atualização do cliente 4.0.105.0

<sup>2</sup> requer que os administradores de ti ativem o Microsoft whiteboard. Além disso, se você tiver uma exibição na frente da sala habilitada para toque, você deve calibrar várias telas de toque usando as configurações do Windows com o login de administrador de dispositivo para começar a usar o Microsoft whiteboard para colaboração de uma exibição de sala compartilhada para uma reunião do teams

### <a name="40850-0482019"></a>4.0.85.0 (04/8/2019)

Apresentado nesta atualização:

- Corrige um problema com o recurso "fornecer comentários" 
- Otimizações em preparação para a atualização do dispositivo futuras salas do Microsoft Teams para a versão 1809 do Windows 10

### <a name="40780-03142019"></a>4.0.78.0 (03/14/2019)

Apresentado nesta atualização:

- Correção do bug "paralisar na inicialização do aplicativo" que afetou os dispositivos na compilação herdada do Windows 10 RS2. 


### <a name="40760-03042019"></a>4.0.76.0 (03/04/2019)

Apresentado nesta atualização:

- Teclado DTMF para reuniões P2P e chamadas PSTN do Microsoft Teams. Para que o Microsoft Teams seja seu cliente de chamadas padrão, os administradores devem definir IsTeamsDefaultClient como true
- Fixar o vídeo de entrada de um participante remoto em tela cheia na frente da exibição da sala. Usar o comando "fixar" da lista de participantes no console
- Melhorias nas notificações de lobby com a adição da notificação na frente da sala
- Ícone de transmissão do painel de exibição de sala removido quando o Beacon do Bluetooth não está habilitado no dispositivo de salas do Microsoft Teams
- Correção de um problema de controle de volume nas reuniões do teams


### <a name="40640-12142018"></a>4.0.64.0 (12/14/2018)

Apresentado nesta atualização:

- Exibir conteúdo na frente da sala (para) é exibido em sistemas de sala de tela dupla
- Melhorias nas interfaces do usuário da sala de ti e na frente
- Suporte do lado do cliente do TLS 1,2. Para clientes locais, a habilitação da comunicação com o TLS 1,2 para salas do Microsoft Teams requer o Skype for Business Server 2015 atualização cumulativa 9 (CU9) ou a atualização cumulativa 1 do Skype for Business Server 2019 (CU1).

### <a name="40510-11172018"></a>4.0.51.0 (11/17/2018)

Apresentado nesta atualização:

- Suporte a duas exibições (na frente da sala) em reuniões do teams 

### <a name="40310-10162018"></a>4.0.31.0 (10/16/2018)

Apresentado nesta atualização:

- Correções de qualidade e confiabilidade

### <a name="40270-1012018"></a>4.0.27.0 (10/1/2018)

Apresentado nesta atualização:

- Alterações de código necessárias para preparar o aplicativo salas do Microsoft Teams para atualização mais recente do Windows 10 versão 1803
- Correção de problemas de formatação com EULAs localizados (especificamente norueguês) que evitam o progresso além da janela de configuração de OOBE do EULA
- Alterações de código necessárias para deixar o aplicativo salas do Microsoft Teams ser executado em sistemas de salas de Lync herdados. Veja mais [aqui](https://aka.ms/lrsupgrade).

### <a name="40190-8312018"></a>4.0.19.0 (8/31/2018)

Apresentado nesta atualização:

- Hotfix para aplicativo Crestron não inicializado, que normalmente estaria acessível quando o botão do aplicativo em um dispositivo Crestron SR estiver pressionado. Salas do Microsoft Teams reinicialização do aplicativo necessário após a instalação do 4.0.19.0.

### <a name="40180-08272018"></a>4.0.18.0 (08/27/2018)

Apresentado nesta atualização:

- Aprimoramentos de recursos do recurso "relatar um problema" no modo de Teams (equivalente a "fornecer comentários" no modo Skype for Business)
- Habilitar a capacidade de retorno do Microsoft Teams para o modo Skype for Business para chamadas SIP
- Melhorias de acessibilidade (narrador, lupa)
- Reinicie o aplicativo automaticamente quando necessário após a aplicação das alterações do provisionamento de XML
- Correções diversas

### <a name="4080-07062018"></a>4.0.8.0 (07/06/2018)

Apresentado nesta atualização:
- Esta atualização permite que as reuniões do Skype for Business *e* do teams ofereçam suporte a dispositivos de sistemas de sala. O Teams está desativado por padrão depois que a atualização é aplicada. Os administradores podem habilitar as equipes localmente nas configurações do dispositivo ou por meio de um push de XML remoto.

### <a name="311150-06182018"></a>3.1.115.0 (06/18/2018)

Apresentado nesta atualização:

- Correção de erro de endereço observado em alguns sistemas durante a inicialização do aplicativo.

### <a name="311130-06132018"></a>3.1.113.0 (06/13/2018)

Apresentado nesta atualização:

- Alterações que permitem à Microsoft gerenciar atualizações do Windows com mais flexibilidade.
- Nenhuma mudança na experiência do usuário final.

### <a name="311120-06052018"></a>3.1.112.0 (06/05/2018)

Apresentado nesta atualização:

- Correção para solucionar problemas de capacidade de resposta do console observados em dispositivos baseados no Surface pro 2017 conectados a dois monitores frontais de sala e inclusão de vídeo
- Verificação automática para garantir que o sistema está executando o último script de provisionamento

### <a name="311040-04162018"></a>3.1.104.0 (04/16/2018)

Apresentado nesta atualização:

- Correção para melhorar o comportamento do OSK (teclado virtual na tela) nos sistemas baseados na versão 1709 do Windows 10
- Melhorias para se preparar para futuras atualizações do sistema operacional

### <a name="311000-03162018"></a>3.1.100.0 (03/16/2018)

Apresentado nesta atualização: 

- Aplicativo atualizado para melhorar a telemetria

### <a name="31990-03142018"></a>3.1.99.0 (03/14/2018)

Apresentado nesta atualização:

- Corrige um problema em que podem ocorrer problemas de junção intermitentes da reunião
- Corrige um problema conhecido para resultar em uma experiência de "travamento" do dispositivo

### <a name="31980-382018"></a>3.1.98.0 (3/8/2018)

Apresentado nesta atualização:

- Correções de bugs/falhas para melhorar a estabilidade
- Suporte para console de tamanho variável
- Descarga de processamento de áudio periférico (lista branca adicional de mídia)
- Otimizações que permitem que os profissionais de ti criem imagens para você mesmo com a atualização de Janeiro do Windows 10, versão 1709 e posterior. 

<!--### 3.1.97.0 (00/00/0000)
Introduced in this update: 
- Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) hardware only. -->

### <a name="30160-11272017"></a>3.0.16.0 (11/27/2017)

Apresentado nesta atualização:

- Corrige um problema com o recurso "fornecer comentários".

### <a name="30150-1032017"></a>3.0.15.0 (10/3/2017)

Apresentado nesta atualização:

- Suporte para hardware de encaixe da [série POLYCOM MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)
- Suporte para o [Logitech brio](https://www.logitech.com/product/brio)
- Resolve um problema em que os modos de exibição (console e frontal da sala) falham ao entrar no modo de suspensão quando não há atividade na sala

### <a name="30120-912017"></a>3.0.12.0 (9/1/2017)

Apresentado nesta atualização:

- É executado em um Tablet da Surface pro (2017) 
- Compatível com a atualização do Windows 10 Enterprise Creator (idioma inglês, Build 1703)
- Suporte para hardware de encaixe [CRESTRON Sr](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system)
- Suporte OEM para controles de ambiente (Crestron)

A versão de 64 bits do Windows 10 Enterprise aniversário Edition (Inglês, versão 1607) não é mais compatível com as salas do Microsoft Teams Release 3.0.12.0 (atualização 3).

### <a name="3080-842017"></a>3.0.8.0 (8/4/2017)

Apresentado nesta atualização:

- Resolve os problemas observados durante a pesquisa de usuários federados por meio do campo de pesquisa de participantes. Antes desta correção, os resultados da pesquisa de usuários federados externos podem não ter resolvido corretamente e, em vez disso, retornar resultados incorretos.

### <a name="3060-772017"></a>3.0.6.0 (7/7/2017)

Apresentado nesta atualização:

- Suporte a tela dupla (para paridade do sistema herdado)
- Temas (temas internos e a capacidade de definir o tema personalizado)
- Capacidade de enviar comentários para compilações públicas
- Telemetria aprimorada em relação à confiabilidade da junção de reunião
- Relatórios do OMS aprimorados
- Capacidade para o administrador de ti configurar dispositivos remotamente
 <!-- - Front-of-Room UX shows room details pre-meeting U2 -->

### <a name="2020-03152017"></a>2.0.2.0 (03/15/2017)

Apresentado nesta atualização:

- Seleção do usuário no aplicativo de áudio da sala de reunião e dispositivos USB de vídeo
- Relatório de status do console de sala integrado para clientes que usam o Microsoft Operations Management Suite, agora o Azure monitor

### <a name="release-to-market-1272016"></a>Lançamento no mercado (12/7/2016)

**Recurso (s):**

 **Projetado para o Skype for Business**

- Reuniões do Skype com apenas um toque
- Experiência de reunião do Skype otimizada para salas com vídeo em HD com preenchimento de tela e áudio de banda larga de alta definição
- Todos os participantes podem se conectar à Reunião do Skype usando o dispositivo que quiserem, onde quer que estejam
- Convide pessoas a partir de seu diretório, onde você pode ver imediatamente a disponibilidade de cada contato, ou por chamada telefônica
- Compatível com os recursos de Conferência e Chamada PSTN do Skype for Business para substituir o telefone de conferência em sua sala

 **Transforme qualquer sala de reunião**
 
- Aplicativo dedicado à Reunião do Skype, otimizado para o controlador de tela touch de centro da mesa e para a grande tela frontal da sala
- Reutilizar investimentos existentes na sua tela inicial ou projetores
- Funciona para todos os tipos de espaços de reunião, de espaços pequenos a grandes salas de conferência
- Os dispositivos de áudio e vídeo certificados do Skype for Business estão disponíveis para vários tamanhos de sala
- Ingestão interna com fio para projetar o compartilhamento de área de trabalho para a sala e para a Reunião do Skype

 **Fácil de implantar, simples de gerenciar**
 
- Aplicativo sempre ativo que ativa automaticamente as exibições quando detecta pessoas na sala
- Implantação e atualização simples do aplicativo de Reunião do Skype da UWP (Plataforma Universal do Windows)
- O Windows AppLocker bloqueia o dispositivo para o aplicativo de Reunião do Skype
- Monitorado e gerenciado como um dispositivo Windows 10 Enterprise por meio do Intune e do Configuration Manager (MDM)
- Confiabilidade de nível empresarial
- Esforço mínimo para usuários finais devido à semelhança com a interface do usuário do Skype
- É executado no tablet Surface Pro 4

<a name="See"> </a> 
## <a name="see-also"></a>Confira também

[Suporte às Salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Preparar seu ambiente](rooms-prep.md)

[Suporte para salas do Microsoft Teams versões de Branch atuais](rooms-lifecycle-support.md)

[Problemas conhecidos para salas do Microsoft Teams](known-issues.md)

[Plano para salas do Microsoft Teams](rooms-plan.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
