---
title: Planejar o painel de controle de qualidade de chamada for Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: 'Resumo: Saiba mais sobre o que considerar ao planejar o painel de controle de qualidade de chamada.'
ms.openlocfilehash: ee82d56747ee4f4241f2630a5a6fd3136ff42be4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217763"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>Planejar o painel de controle de qualidade de chamada for Skype para Business Server 
 
**Resumo:** Saiba mais sobre o que considerar ao planejar o painel de controle de qualidade de chamada.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>Visão geral do Skype para painel de qualidade de chamada do Business Server

O Skype para Business Server chamada qualidade Dashboard (CQD) é uma camada de relatório na parte superior de qualidade da experiência do banco de dados no Monitoring Server Skype para Business Server. CQD usa o Microsoft SQL Server Analysis Services para fornecer uso agregado e informações de qualidade, bem como para filtragem e dinamização no conjunto de dados de chamadas. CQD recursos incluem:
  
- **Armazenamento de arquivamento de dados de QoE via o componente de CQD arquivamento de QoE.** O componente de arquivo morto do QoE pode armazenar dados de QoE por um período maior que o pode Monitoring Server. Isso permite tendências e relatórios por até sete meses de dados ao mesmo tempo, com a capacidade de slide a janela relatório como até onde trás como não há dados.
    
- **Relatório e análise usando a alimentação e a velocidade do Microsoft SQL Server Analysis Services.** CQD utiliza o Microsoft SQL Analysis Services para fornecer resumo fast, filtro e dinamização capacidades fortalecer o painel por meio de um cubo de análise. Velocidade de execução e a capacidade de fazer uma busca detalhada nos dados de relatórios podem reduzir drasticamente o tempos de análise.
    
- **Novo esquema de dados otimizada para relatórios de qualidade de chamada.** O cubo tem um esquema projetado para relatórios de qualidade de voz e investigações. Os usuários do portal podem se concentrar nas tarefas de relatórios, em vez de para saber como as métricas de QoE do banco de dados mapas de esquema para os modos de exibição que precisam. A combinação entre o arquivamento de QoE e o cubo fornece uma abstração que reduz a complexidade do relatório e análise via CQD. O esquema de banco de dados de arquivamento do QoE também contém tabelas que podem ser preenchidas com dados de implantação específicos para aumentar o valor geral dos dados.
    
- **Designer de relatório interno e a edição de relatório de in-loco.** O componente de Portal vem com vários relatórios internos modelados após a metodologia de qualidade de chamada. Os usuários do portal podem modificar os relatórios e criar novos relatórios através da funcionalidade de edição do Portal.
    
- **Acesso de API da Web para a estrutura de relatório e análise de dados de cubo.** A estrutura de relatórios do painel não é a única maneira de exibir os dados do cubo. CQD fornece vários exemplos do uso de HTML e JavaScript para recuperar dados das APIs do Web CQD e processar os dados em um formato personalizado. A combinação do Editor de relatório e as APIs de Web CQD permite a rápida criação de protótipos de relatórios e layout de relatório personalizado.
    
## <a name="cqd-design-goals"></a>Metas de Design CQD

O CQD permite que os profissionais de TI utilizem dados agregados para identificar áreas de foco em seu ambiente com problemas de qualidade de mídia. Ele permite que um profissional de TI compare estatísticas de diferentes grupos de usuários e identifique tendências e padrões. O foco não está em resolver problemas de chamadas individuais, mas em identificar problemas e soluções que se apliquem a muitos usuários em um determinado ambiente. 
  
## <a name="call-quality-dashboard-components"></a>Componentes do painel de qualidade de chamada

O painel de controle de qualidade de chamada consiste em vários bancos de dados, Microsoft SQL Agent trabalhos, processos e aplicativos da web. Os trabalhos do agente do Microsoft SQL periodicamente copiem os dados do banco de dados de métricas de QoE o banco de dados de arquivamento do QoE e processos de cubo com os dados no banco de dados de arquivo morto de QoE. O banco de dados de repositório armazena as definições de relatório que o Portal a energia. O Portal fornece acesso de navegador para os dados do cubo. 
  
Os componentes CQD, incluindo os bancos de dados do repositório, cubo e arquivamento de QoE, podem ser instalados no servidor de monitoramento, instalados em seu próprio servidor ou instalados em vários servidores. O método de instalação específica depende as exigências de desempenho de CQD, bem como o impacto para outros processos nos mesmos servidores. Para obter mais informações, consulte a seção "Componentes e topologias para CQD" neste artigo.
  
### <a name="architectural-overview"></a>Visão geral da arquitetura

Resumindo, CQD requer os seguintes elementos:
  
- Dois bancos de dados: um banco de dados de arquivamento e um banco de dados do repositório.
    
- Visualizando de um cubo do SSAS dados agregados 
    
- O IIS hospeda CQD Portal da Web
    
![Componentes CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
A mesma arquitetura CQD suporta o Lync Server 2013 e Skype para negócios. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD e Skype para negócios versus Lync 2013

 Em um Skype para apenas o ambiente de negócios, os seguintes recursos estão disponíveis:
  
- Geração de relatórios de Wi-Fi de intensidade do sinal
    
- Geração de relatórios de Wi-Fi de drivers de Chipset
    
- Classifique os meus dados de chamada 
    
## <a name="information-available-through-cqd"></a>Informações disponíveis por meio de CQD

CQD pode mostrar Skype para Business Server áudio, vídeo e contagens de fluxo e contagem de boa versus chamadas ruim, bem como taxas de chamadas ruim para boa de compartilhamento de aplicativos. Os modos de exibição podem ser subconjuntos e filtrados por muitas dimensões diferentes. CQD desenha dados do banco de métricas de QoE Monitoring Server. Então, os dados são mesclados com quaisquer dados fornecido pelo cliente, como o mapeamento de criação de sub-rede de rede para que seja possível relatórios como "Chamada qualidade por edifício". 
  
CQD também abstrai muitas das Idiossincrasias de dados de QoE internas, como "chamador" e "chamado", de forma que o usuário pode se concentrar na criação de modos de exibição de relatório em torno "server" e "cliente". Após a metodologia de qualidade de chamada CQD é simplificado a fim de ajudar a identificar as condições que pacotes de chamadas ruins têm em comum — um dos princípios para melhorar a qualidade da chamada.
  
## <a name="viewing-data-in-cqd"></a>Exibindo dados em CQD

Os dados CQD podem ser exibidos através do Portal de CQD e pode ser acessados por meio de chamadas da API REST.
  
### <a name="cqd-portal"></a>Portal CQD

O Portal é a maneira mais rápida para exibir os dados no cubo. O Portal vem com vários relatórios internos que são utilizáveis imediatamente. Os relatórios internos estão vinculados uma maneira estruturada para guiar o usuário para sucessivamente menores e menores subconjuntos dos dados de chamada. Os relatórios internos também destacam as várias maneiras diferentes, que os dados possam ser exibidos demonstrando uma combinação de gráficos e tabelas com diferentes dinamização, filtros e medidas. Cada usuário que acessa o Portal pode ter seu próprio conjunto de relatórios que ele/ela pode modificar e compartilhar. Para obter mais informações sobre o uso do Portal do Web CQD, consulte o [Painel de qualidade de chamada de uso do Skype para Business Server](use.md).
  
Sistemas operacionais suportados para o Portal CQD: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 e Windows Server 2016 (Skype para Business Server 2019 CQD apenas).
  
Navegadores compatíveis com do Portal CQD: Internet Explorer 11, o Internet Explorer 10 e o Internet Explorer 9.
  
### <a name="rest-apis"></a>APIs REST

Os dados do cubo também podem ser acessados por meio de chamadas da API REST. Os dados recuperados via as chamadas da API REST podem ser renderizados via páginas HTML. Os usuários podem levar aproveita a velocidade de consulta e o esquema de alto nível da CQD enquanto ainda criar relatórios personalizados adequados para suas necessidades de negócios. Para obter mais informações sobre a API e os exemplos, consulte [Desenvolver painel de qualidade de chamada do Skype para Business Server](develop.md). 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>Definindo os requisitos da sua organização para CQD

CQD fornece uma análise de profundidade e rápida e arquivamento de dados de QoE de dados de qualidade de chamada. O guia a seguir ajuda a decidir quando e por que você faria implantar CQD.
  
### <a name="when-to-deploy-cqd"></a>Quando implantar CQD

 **CQD pode ser implantado para estabelecer uma medida de qualidade de chamada de linha de base, mesmo se uma organização não ter problemas de qualidade de chamada.** Estabelecer uma medida de qualidade de chamada de linha de base é importante, porque cada organização tem uma combinação diferente de Wi-Fi versus com fio e remotos versus trabalhadores no escritório. Quando surgem os problemas de qualidade de chamada, as medidas de qualidade de chamada mais recentes podem ser comparadas a intervalos de tempo anterior. Recursos de tendências do CQD permitem detecção fácil das alterações na qualidade de chamada ao longo do tempo.
  
 **CQD pode ser implantado para localizar proativamente as áreas de problema que podem afetar a qualidade da chamada.** Mesmo que a média de chamadas qualidade para uma organização pode cumprir os objetivos definidos pela organização, pode haver alguns problemas de qualidade de chamada que estão ocultos por trás de métricas médios. CQD permite divisão do tipo tabela dinâmica métricas de qualidade de chamada por um número de dimensões no banco de dados QoEMetrics. Reconhecimento de destaques em grupos de ponto é uma maneira rápida de forma proativa localizar os problemas de qualidade de chamada.
  
 **CQD deve ser implantado se houver chamada problemas de qualidade na organização para reduzir o tempo necessário para solucionar problemas.** CQD pode simplificar investigações de qualidade de chamada existente, oferecendo fast relatórios de desempenho e recursos de detalhamento dinâmico. CQD foi projetado para muitos tipos de fluxos de trabalho na validação de investigações de qualidade de chamada de reparos no ambiente.
  
### <a name="why-deploy-cqd"></a>Por que implantar o CQD

 **CQD deve ser implantado se o relatório de QoE precisa acontecer por mais de 3 meses de dados.** O banco de dados QoEMetrics e relatórios do monitoring server foram projetados para manter e relatar a um pequeno conjunto de dados. O banco de dados de métricas de QoE é otimizado para o fast inserções, e, portanto, relatórios de desempenho pode ser impedido por um grande volume de chamadas ou concorrente acesso de relatório no banco de dados. Banco de dados de arquivo morto de QoE do CQD fornece uma segunda cópia dos dados de métricas de QoE com muito mais recursos de retenção. O Portal também é otimizado para mostrar até 7 meses de dados de cada vez e pode relatar em todos os dados no arquivamento QoE, conforme necessário.
  
 **CQD deve ser implantado se os relatórios de QoE personalizados forem necessários.** O Portal possui um recurso de Editor de relatório para relatórios de criação e a criação de protótipos rapidez e facilidade. Ele também torna disponível APIs REST para acesso programático para os dados de cubo, permitindo que a apresentação personalizada usando HTML/JavaScript ou muitas outras estruturas. Não é necessário criar novas consultas SQL para fins de criação de modos de exibição de dados personalizados para geração de relatórios.
  
 **CQD deve ser implantado se a funcionalidade de relatório de QoE existente não atender a velocidade ou a profundidade necessários para a organização.** CQD vem com vários relatórios internos. Os relatórios são imediatamente úteis e demonstrar como progressivamente detalhando os dados pode oferecer insights adicionais em cada nível. A hierarquia de relatórios também ajuda a gerenciar os vários relatórios de maneira lógica e incentiva a criação de relatórios mais muitos que são facilmente acessada e compreensível. CQD não oferece apenas velocidade e flexibilidade, mas também é otimizado para os fluxos de trabalho desenvolvidos pela metodologia de qualidade da chamada.
  
## <a name="components-and-topologies-for-cqd"></a>Componentes e topologias para CQD

CQD vem com vários componentes, e ele o ajuda a entender os requisitos de cada componente e elas se relacionam uns com os outros para obter a implantação mais simples e com melhor desempenho da ferramenta. A tabela a seguir descreve o componente dependente para cada componente CQD.
  

|**Nome do componente**|**Componente dependente**|
|:-----|:-----|
|Arquivo morto de QoE  <br/> |Microsoft SQL Server  <br/> |
|Cubo  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|Portal  <br/> |Serviços de informações da Microsoft  <br/> |
|Serviço de repositório (parte da instalação do Portal)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> Para arquivar de QoE e o cubo, determinadas opções de implantação exigem edições de Business Intelligence ou Enterprise do Microsoft SQL Server. Consulte a seção [requisitos de infraestrutura para CQD](plan.md#Infrastructure_Req) abaixo para obter mais detalhes.
  
![Componentes CQD](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>Configuração de servidor único

Todos os componentes CQD e componentes dependentes podem ser instalados em uma máquina. A configuração de caixa única é a configuração mais simples e permite que CQD ser autônomos. CQD apenas seria precisam acessar o banco de dados de métricas de QoE no Monitoring Server. O servidor de CQD pode ser uma máquina autônoma, uma máquina virtual, ou ainda pode ser o Monitoring Server, dependendo de recursos disponíveis nesses máquina host e os requisitos de desempenho. 
  
Durante a instalação, o usuário executando que a instalação simplesmente precisa fornecer o Microsoft SQL Server e instâncias de Microsoft SQL Server Analysis Services que tenham sido anteriormente configuradas na máquina onde o CQD deve ser instalado. Para [Implantar o painel de qualidade de chamada do Skype para Business Server](deploy-0.md) , consulte para obter mais informações.
  
### <a name="multiserver-configuration"></a>Configuração multiservidor

Em uma configuração multiservidor, o arquivamento de QoE, cubo e Portal podem estar todos em máquinas diferentes. Existem dois usos principais para a configuração multiservidor:
  
- Hospedando o Portal da Web CQD e CQD cubo em servidores diferentes.
    
- Hospedando um Portal separado da produção"" Portal "desenvolvimento". 
    
  **Hospedando o Portal da Web CQD e CQD cubo em máquinas diferentes.** As organizações que talvez tenham requisitos para separar o Portal CQD da instalação do SQL Server ou que talvez queira combinar e adequar edições do SQL Server para a instância do SQL Server e a instância do SQL Server Analysis Services podem optar por instalar o Portal CQD e Cubo de CQD em máquinas diferentes. O componente de arquivo morto do QoE também pode ser o único componente CQD que foi instalado, se a organização simplesmente quer ter um método sustentável para arquivar os dados do QoE sem atingir os limites de desempenho no Monitoring Server.
  
![Servidor único CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **Hospedando um Portal separado da produção"" Portal "desenvolvimento".** As organizações que desenvolvem seus próprios relatórios personalizados (via APIs REST) talvez prefira implantar instâncias adicionais do Portal (CQD) junto com a produção de Portal que usuários regulares acessam para monitoramento da qualidade de chamada ou investigações. O Portal de desenvolvimento pode isolar quaisquer modificações no portal do ambiente de produção. Os portais da web adicionais podem ser implantados em máquinas diferentes (mostradas abaixo) ou implantados no diretórios web diferente na mesma máquina (não mostrados). Para realizar o último, o portal da web CQD adicional deve ser copiado para a máquina de produção manualmente porque o processo de instalação CQD sempre implanta o Portal da Web CQD o site padrão com nomes de aplicativo da web predefinido.
  
![Planejar CQD Multi Server](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>Topologias suportadas

CQD não mescle dados de vários bancos de dados QoEMetrics, como é o caso onde há vários Skype para topologias de servidor de negócios, cada um com seu próprio Monitoring Server. Cada instância CQD deve apontar para um banco de dados QoEMetrics. No entanto, pois CQD serão transferidos grande parte da carga de trabalho de relatórios do Monitoring Server, grandes organizações que são necessárias para implantar um Monitoring Server por Skype para topologia de servidores corporativos devem considerar o uso de um Monitoring Server para todas as topologias.
  
## <a name="infrastructure-requirements-for-cqd"></a>Requisitos de infraestrutura para CQD
<a name="Infrastructure_Req"> </a>

CQD, incluindo todos os seus componentes e os componentes dependentes, pode ser implantado em uma máquina virtual, um único computador ou em várias máquinas. Os requisitos mínimos de hardware e software estão listados abaixo. Disponibilidade de dados e consulta de desempenho pode variar de minutos ou horas, dependendo do número de ativo Skype para usuários corporativos Server e o hardware e configuração, portanto, algumas medições de desempenho são fornecidas abaixo.
  
|||
|:-----|:-----|
|Sistemas operacionais suportados  <br/> |Windows Server 2008 R2, Windows Server 2012, o Windows Server 2012 R2  <br/> |
|Com suporte do SQL Server  <br/> |SQL Server 2012, SQL Server de 2014, 2016 do SQL Server  <br/> |
   
CQD utiliza Microsoft SQL Server, o Microsoft SQL Server Analysis Services e o Microsoft Internet Information Services, portanto, do CQD mínimo requisitos de hardware e software são basicamente o mesmo que esses componentes dependentes. No entanto, com base nos requisitos da organização em torno de atualização de dados (que depende em parte o volume de dados de QoE que gera a organização) e os custos de implantação, considerações de implantação adicional devem ser feitas.
  
Processamento de dados no CQD é separado em duas etapas principais: 
  
- Processo de arquivamento de QoE
    
- Processamento do cubo CQD
    
  **Processamento de arquivo morto QoE.** A tarefa de processamento de arquivo morto do QoE copia os dados do banco de dados de métricas de QoE no Monitoring Server no banco de dados de arquivo morto de QoE. Há duas situações em que o tempo de processamento da tarefa teria características de desempenho fundamentalmente diferente. A primeira é após a instalação inicial do CQD. Quando a tarefa é executada pela primeira vez, após uma instalação nova, a tarefa de processamento de arquivo morto do QoE copiará todos os dados que está no banco de dados de métricas de QoE em banco de dados de arquivo morto de QoE. O segundo é o processamento periódico após essa fase inicial. O arquivamento de QoE Processando tarefa será executado a cada 15 minutos e processar quaisquer novos registros de QoE que estão no banco de dados de métricas de QoE. Geralmente, o tempo de processamento inicial não é uma preocupação porque ele é executado somente na primeira vez, quando CQD está instalado. No entanto, se o servidor CQD for está seriamente em fornecidos, essa tarefa pode levar várias horas. Consulte a tabela abaixo por exemplo inicial arquivamento de QoE tempos de processamento.
  
  **Processamento de cubo do CQD.** A tarefa de processamento de cubo agrega os dados do banco de dados de arquivamento do QoE no cubo. O tempo de processamento de cubo inicial e o tempo de processamento de cubo subsequentes são determinados pela edição do SQL Server Analysis Services usada para o cubo CQD. Se for usado o Standard edition, não há nenhuma diferença entre o tempo de processamento de cubo inicial e o cubo subsequente tempo de processamento, porque cada vez que os dados de cubo são atualizados, ele sempre será um processamento completo de todos os dados disponíveis. (Isso significa que o tempo de processamento de cubo aumenta à medida que a quantidade de dados no banco de dados aumenta arquivamento QoE). Porque o Business Intelligence Edition e Enterprise Edition do SQL Server têm partição suporte, se qualquer edição for usada, somente a executar inicial processará todos os dados no banco de dados de arquivo morto de QoE. Em execuções subsequentes, quando a tarefa for disparada a cada 15 minutos, a tarefa processará apenas os novos registros adicionados ao banco de dados de arquivamento do QoE desde a última vez em que a tarefa foi executada. Uma vez por dia, também haverá um processamento completo na partição que contém os dados do mês atual.
  
As características de máquina física podem afetar o desempenho de CQD, bem como os recursos de software que estão disponíveis a partir dos componentes do SQL Server. O componente de arquivo morto do QoE será mais intensivos de disco em comparação com outros componentes, enquanto o componente do cubo será mais CPU e memória intensiva. Todos esses fatores contribuem para o tempo de processamento de dados total do CQD, que afeta diretamente a disponibilidade e a atualização de dados. Organizações devem tomar decisões sobre o hardware e software com base nas necessidades individuais da organização. 
  
### <a name="tested-hardware-configurations"></a>Configurações de Hardware testada

Esta seção torna a pressuposição de que há um único banco de dados QoEMetrics no ambiente. 
  
**Perfis de máquina**

|**Máquina**|**Núcleos de CPU**|**RAM**|**Cubo no mesmo disco e arquivamento de QoE**|**Arquivo morto do QoE e SQL Temp DB no mesmo disco**|
|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |4  <br/> |7 GB  <br/> |Sim   <br/> |Sim  <br/> |
|4 núcleos  <br/> |4  <br/> |20 GB  <br/> |Sim  <br/> |Não  <br/> |
|8 núcleos  <br/> |8  <br/> |32 GB  <br/> |Sim  <br/> |Não  <br/> |
|16 núcleos  <br/> |16  <br/> |128 GB  <br/> |Não  <br/> |Não  <br/> |
   
**Resultados de desempenho**

|**Máquina**|**Tamanho do BD de métricas de QoE**|**Partições SQL**|**Tipo de disco**|**Número de fluxos**|**Processo inicial de arquivo morto**|**Processo inicial de cubo**|**Processo de arquivamento subsequente**|**Processo de cubo subsequente**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Máquina virtual  <br/> |900 MB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |M.5  <br/> |m 30  <br/> |2C  <br/> |30 s  <br/> |1M  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho variável)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1M  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |9 GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |5 M  <br/> |2º semestre  <br/> |5 m  <br/> |1M  <br/> |5 m  <br/> |
|Máquina virtual  <br/> |30 + GB  <br/> |Único  <br/> |VHD (tamanho fixo)  <br/> |10 M  <br/> |h 15  <br/> |20 m  <br/> |2C  <br/> |45 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Único  <br/> |Vários discos  <br/> |5 M  <br/> |2º semestre  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|8 núcleos  <br/> |9 GB  <br/> |Vários  <br/> |Vários discos  <br/> |5 M  <br/> |2º semestre  <br/> |15 m  <br/> |35 s  <br/> |2C  <br/> |
|8 núcleos  <br/> |30 + GB  <br/> |Único  <br/> |Vários discos  <br/> |20 M  <br/> |h 9  <br/> |20 m  <br/> |1M  <br/> |20 m  <br/> |
|8 núcleos  <br/> |30 + GB  <br/> |Vários  <br/> |Vários discos  <br/> |20 M  <br/> |h 9  <br/> |m 30  <br/> |2C  <br/> |2C  <br/> |
|4 núcleos  <br/> |200 GB  <br/> |Único  <br/> |Vários discos  <br/> |M 125  <br/> |6 + dias  <br/> |h 7  <br/> |2C  <br/> |h 6  <br/> |
|16 núcleos  <br/> |500 GB  <br/> |Vários  <br/> |Múltiplos eixos  <br/> |250 M  <br/> |8 dias  <br/> |2º semestre  <br/> |2C  <br/> |10 m  <br/> |
   
\*Eles não deverão ser encontrado em implantações reais porque o banco de dados de métricas de QoE teria que ter 9 e 18 meses de dados, respectivamente, mas eles fornecidas aqui para preservar a integridade.
  
### <a name="service-account-requirements"></a>Requisitos de conta de serviço

Você precisará de uma conta que o agente do SQL no servidor CQD pode usar para importar dados para o QoEArchiveDB (com acesso de leitura ao QoEMetrics).
  
Você também pode precisar configurar uma conta separada para um trabalho de SSAS para extrair dados de QoEArchiveDB (isto é um processo opcional).
  
IIS mais comumente usa o serviço de rede como identidade do Pool de aplicativos, mas pode ser configurado para uma conta de serviço.
  
### <a name="portal-access-control"></a>Controle de acesso ao portal

Por padrão, qualquer usuário autenticado tem acesso. Isso pode ser alterado usando regras de autorização do IIS para restringir a um grupo específico.
  
### <a name="pre-install-requirements"></a>Requisitos anteriores à instalação

Estas instruções pressupõem que um banco de dados de métricas de QoE já tenha sido instalado e é executada em algum lugar do Skype para a topologia de servidor de negócios.
  
#### <a name="hardware-requirements"></a>Requisitos de hardware

CQD utiliza o Microsoft SQL Server, análise do Microsoft SQL Server e Microsoft Internet Information Server portanto do CQD mínimo requisitos de hardware e software são basicamente o mesmo que esses componentes dependentes. No entanto, com base nos requisitos da organização em torno de atualização de dados (que depende em parte o volume de dados de QoE que gera a organização) e os custos de implantação, considerações de implantação adicional devem ser feitas.
  
#### <a name="software-requirements"></a>Requisitos de software

Os seguintes sistemas operacionais são necessários para CQD:
  
- Windows Server 2008 R2 com o IIS 7.5
    
- Windows Server 2012 com IIS 8.0
    
- Windows Server 2012 R2 com o IIS 8,5

- Windows Server 2016 com o IIS 10.0 (Skype para Business Server 2019 CQD somente)
    
Estes são os serviços de função do IIS necessários (em ordem hierárquica):
  
- Servidor Web
    
  - Recursos HTTP Comuns
    
  - Conteúdo estático
    
  - Documento padrão
    
  - Desenvolvimento do aplicativo
    
  - ASP.NET
    
  - Filtros ISAPI
    
  - Integridade &amp; diagnósticos
    
  - Log HTTP
    
  - Segurança
    
  - Autorização de URL
    
  - Autenticação do Windows
    
  - Ferramentas de gerenciamento
    
  - Console de gerenciamento IIS
    
> [!NOTE]
>  Observe que o seguinte para as versões de requisitos: gt _ 3.5 e 4.5 acima do .net framework está disponível. Ambos são necessários (mais especificamente, 3.5 SP1 é necessário) .> em alguns sistemas, se o ASP.NET esteja configurado antes de instalar o IIS, e em seguida, ASP.NET não podem ser registrados no IIS. Manifestos de problema por meio de ausência de pools de aplicativos para a versão de .net correspondente e também não tiver a versão de .NET CLR na configuração de pool de aplicativos. Para corrigir esse tipo de problema no Windows Server 2008 R2, execute `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`. No Windows Server 2012 e Windows Server 2012 R2, executar `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` seguido removendo o "ServiceModel" módulo do Site da Web padrão nas ferramentas de gerenciamento do IIS Manager.> é opcional, mas recomendado.
  
Para instalar esses requisitos usando o PowerShell, execute o seguinte:
  
```
import-module servermanager
```

```
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

Há suporte para as seguintes versões do SQL Server:
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017
    
Business Intelligence ou Enterprise edition é recomendável por razões de desempenho. Nestas edições permitem o uso de vários arquivos de partição que podem ser processados em paralelo, o que é vantajoso para processar dados relativos a vários meses ou mais. 
  
Embora não seja recomendável, Standard edition é suportado também. Processamento serão restritos a uma única partição (que precisa ser configurado durante a instalação). 
  
Em todos os casos, "Serviços de mecanismo de banco de dados" e "Analysis Services" devem ser instalados. É recomendável, mas não é necessário instalar também o recurso "Ferramentas de gerenciamento - concluir", que adiciona suporte a SQL Server Management Studio Analysis Services. Tela de seleção de recurso deve se parecer com a figura.
  
![Requisitos de recurso do SQL Server](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
Ao configurar a instalação do SSAS, em configuração do Analysis Services, defina "Modo de servidor" para "Multidimensional e Data Mining modo". 
  
Para obter ajuda adicional na instalação e configuração de recursos de Business Intelligence do SQL Server, consulte [Instalar o Analysis Services no modo de mineração de dados e Multidimensional](https://msdn.microsoft.com/en-us/library/ms143708%28v=sql.110%29.aspx).
  
#### <a name="account-requirements"></a>Requisitos de conta

Três contas de serviço de domínio são recomendadas para o princípio do menor privilégio: 
  
- Um que já tenha uma entidade de segurança de logon para o banco de dados de métricas de QoE (com privilégios de db_datareader) e uma entidade de segurança de logon na instância do QoE Archive SQL Server (necessário para criar um objeto de servidor vinculado durante a instalação). Essa conta será usada para executar a etapa de "Dados de arquivamento do QoE" do trabalho de SQL Server Agent.
    
- Um que será usada para executar a etapa "Processo cubo" do trabalho de SQL Server Agent. A instalação criará um logon entidade de segurança ao banco de dados de arquivo morto de QoE (com leitura e gravação com privilégios) e também cria um membro à função de QoE (com privilégios de controle total) para o cubo.
    
- Um que será usada para executar o processo de trabalho do IIS para o web APIs e portais da web. A instalação criará um logon entidade de segurança para o banco de dados de arquivamento de QoE (com privilégios de leitura), uma entidade de segurança de logon para o banco de dados de repositório (com leitura e gravação com privilégios) e um membro no QoERole (com privilégios de controle total) para o cubo. 
    
    > [!NOTE]
    > Quando o banco de dados de arquivamento do QoE e o banco de dados de repositório estiverem hospedados no mesmo servidor SQL, somente uma segurança de logon principal com dois mapeamentos do usuário é criada. 
  
As duas primeiras contas poderá ser consideradas logicamente como "contas de serviço de back-end" e o último é uma conta de serviço"front-end". Embora não seja recomendável, é possível usar uma única conta em todos os casos.
  
> [!NOTE]
> A conta de usuário iniciar a instalação deve ter acesso de leitura ao banco de dados de métricas de QoE também (além de ter direitos de administrador da máquina no servidor de banco de dados de arquivo morto de QoE onde a instalação deve ocorrer). 
  
## <a name="capacity-planning"></a>Planejamento de capacidade
<a name="Infrastructure_Req"> </a>

CQD foi projetado para minimizar o impacto na QoEMetrics: o código foi otimizado para não bloquear dados e trabalhos de importação são ajustáveis.
  
O tipo de hardware para usar depende seus requisitos para a rapidez sincronizações deverá ser executado. Dimensionamento de disco é da seguinte maneira:
  
- QoEArchive é ~1.5x maior QoEMetrics DB inicialmente
    
- Cubo de SSIS compacta os dados quase 10 x comparado ao DB
    
- Os dados são particionados mensalmente; as partições podem ser excluídas.
    

