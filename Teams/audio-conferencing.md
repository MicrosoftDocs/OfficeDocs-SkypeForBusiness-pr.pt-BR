---
title: Orientações práticas de Audioconferência no Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: Orientações práticas para planejar, implantar e gerenciar a Audioconferência no Microsoft Teams usando a estrutura Concepção (planejamento), Integração (fornecimento), Geração de valor (operação).
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: 0bf506350a6e656d0143a968bcd0e884b47e5653
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120680"
---
<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a>Orientações práticas de Audioconferência no Microsoft Teams
============================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

A Audioconferência do Office 365  permite que os participantes ingressem em reuniões do Microsoft Teams usando qualquer telefone.

Eis o que você obtém com a [Audioconferência](https://go.microsoft.com/fwlink/?linkid=858992) no Office 365.

Esta orientação prática você será levado o cliente do Office 365 FastTrack framework jornada e seus três fases, Envision, integrado e o valor de unidade, para ajudá-lo a planejar, entregar e operar uma implementação de conferência de áudio na direção de negócio bem-sucedido resultados.

> [!TIP]
> Nessas orientações práticas, fornecemos exemplos de resultados de cada atividade e discussão importante. Os exemplos contidos neste documento estão incluídos nos balões de DICAS e servem como um modelo que você pode reutilizar. Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.

Concepção <a name="Envision_AudioConferencing"> </a>
=========

A fase de Concepção oferece a base a jornada do cliente Office 365 e se aplica a todas as cargas de trabalho, como a Audioconferência.

Nessa fase, os objetivos de negócios são estabelecidos com as partes envolvidas relevantes do projeto reunidas, para entregar:

-   Um plano de sucesso e de alto nível que tenha casos de uso comercial, as principais partes envolvidas, os objetivos e os resultados principais (OKRs), os principais indicadores de sucesso (KSIs), os riscos, a avaliação do ambiente, a prontidão para adoção e o plano operacional.

-  Um plano detalhado de implementação técnica da Audioconferência para atingir o estado final desejado.

<a name="define-business-use-cases-for-audio-conferencing"></a>Definição de casos de uso comercial para Audioconferência
------------------------------------------------

A Audioconferência oferece à organização pontos de entradas adicionais para todas as reuniões (ad hoc e agendadas), permitindo que os participantes ingressem via PSTN (Rede Telefônica Pública Comutada) discando pelo telefone fixo tradicional, PBX ou telefones celulares.

Isso é útil quando o organizador ou os participantes não estão na frente do computador ou quando as conexões de dados estão indisponíveis ou não são confiáveis para o suporte a comunicações de voz, como em áreas remotas com cobertura irregular de dados móveis ou conexão a um serviço de Wi-Fi público com largura de banda limitada, ou quando os participantes da reunião preferem discar para a reunião usando o endpoint de telefonia que possam acessar prontamente.

Nessa etapa, as principais partes envolvidas no projeto definirão os casos de uso comercial que suportem a implementação de Audioconferência.

Os casos de uso comercial devem definir e documentar os resultados comerciais esperados e mensuráveis, e incluir o que segue:

-   Descrição do processo comercial atual
-   Definição dos desafios com os processos comerciais existentes
-   Como a tecnologia pode ajudar a superar esses desafios
-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

> [!TIP]
> Segue um exemplo de caso de uso comercial concluído:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.|
> |**Desafios com os processos comerciais existentes**<br>A Contoso gasta cerca de US$ 1 milhão por ano com o serviço de conferência PSTN atual, com 75% do custo incorrendo para reuniões internas.<br>O uso dos endpoints tradicionais de telefonia para entrar em reuniões hospedadas pelo serviço de conferência PSTN não está alinhado com o plano de a organização adotar o Teams como uma plataforma de colaboração e comunicação moderna.|
> |**Como a tecnologia pode superar esses desafios**<br>Com a adoção do Microsoft Teams como uma plataforma de colaboração e comunicação moderna, espera-se que os usuários internos participem principalmente de reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião. O serviço de Audioconferência estará disponível para ter suporte para participantes externos ou situações em que o uso do áudio do PC não seja favorável para os participantes internos.|
> |**Resultados comerciais esperados e mensuráveis**<br>A mudança para o Teams como uma plataforma de colaboração e comunicação moderna, aliada ao serviço de Audioconferência, reduzirá consideravelmente o custo de entrega do serviço de conferência PSTN, ao ponto que a Contoso deverá gastar apenas cerca de 20% do custo anual do serviço de conferência PSTN existente.|

Além de definir seus casos de uso comercial, conforme você passa para etapa seguinte da fase de Concepção, também deve ter mais clareza sobre:
- escopo organizacional e
- cronogramas do projeto

<a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas
-------------------------

Os casos de uso comercial definidos na etapa anterior incluirão o escopo organizacional da implementação da Audioconferência e, com base nisso, a matriz abrangente das partes envolvidas pode ser completada para incluir as pessoas certas a serem envolvidas no projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
> 
> |                 Função                  |                                                                                                                                                                                                                                                                Descrição                                                                                                                                                                                                                                                                 | Nome, informações de contato, localização |
> |---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|
> |       Patrocinador executivo do projeto       | <ul><li>A autoridade e a responsabilidade final pelo projeto e pela entrega dos objetivos do projeto</li><li>Ajudar a solucionar problemas escalados pelo Líder do projeto</li><li>Comunicação do patrocinador internamente na empresa sobre os objetivos do projeto</li><li>Responsável pela tomada de decisões estratégicas</li><li>Responsável pela disponibilidade do orçamento e dos recursos necessários</li><li>Liderança da avaliação trimestral de negócios (QBR)</li><li>Aceitação e ajuda nos esforços da campanha de conscientização</li><li>Atuando como patrocinador do projeto de distribuição do programa</li></ul> |                 TBA                 |
> |             Líder de projeto              |                   <ul><li>Gerenciamento e liderança da equipe do projeto</li><li>Coordena os parceiros e as equipes de trabalho envolvidos no projeto</li><li>Responsável pela criação e pelo gerenciamento dos planos do projeto para atingir os principais resultados trimestrais</li><li>Solucionar problemas multifuncionais</li><li>Passar atualizações regulares aos patrocinadores do projeto</li><li>Incorporação dos aspectos de adoção em todo o plano do projeto</li><li>Liderança das avaliações mensais de negócios e operações (MBR), contribuindo com as avaliações trimestrais de negócios</li></ul>                   |                 TBA                 |
> |     Líder/arquiteto de colaboração      |                                                                       <ul><li>Responsável pela execução da estratégia de colaboração definida pelos executivos da empresa</li><li>Analisar e escolher produtos de colaboração para a empresa que atendam aos objetivos de negócios</li><li>Responsável pela concepção das operações dos produtos de colaboração</li><li>Define o modelo de operação e suporte</li><li>Contribuir com as avaliações trimestrais de negócios</li><ul>                                                                        |                 TBA                 |
> |              Consultor               |                                                                                                                                                                                                               <ul><li>Responsável pelos serviços de configuração</li><li>Contribui na arquitetura geral da solução</li></ul>                                                                                                                                                                                                                |                 TBA                 |
> |            Gerente de projetos            |                                                      <ul><li>Desenvolvimento e manutenção do plano do projeto</li><li>Gerenciar os produtos finais do projeto de acordo com o plano do projeto e o orçamento</li><li>Registrar e gerenciar os problemas de projeto, incluindo o dimensionamento</li><li>Conduzir chamadas stand up semanais</li><li>Conectar-se e passar atualizações para patrocinadores executivos do projeto</li><li>Trabalhar com o Arquiteto para definir a abordagem de gerenciamento de mudanças e os planos de comunicação</li></ul>                                                       |                 TBA                 |
> | Especialista em adoção/gerenciamento de mudanças |                                                                                       <ul><li>Alimentar a fase de Descoberta em processos de treinamento e adoção</li><li>Participar do workshop de estratégia de adoção</li><li>Desenvolvimento e responsabilidade pela estratégia de adoção</li><li>Desenvolvimento e execução do plano de comunicação</li><li>Responsável por ministrar treinamentos aos usuários finais</li><li>Coletar feedback e conduzir pesquisas</li></ul>                                                                                        |                 TBA                 |
> |             Líder de rede              |                                                                                                                                                              <ul><li>Alimentar a fase de Descoberta em design de rede</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de rede durante a execução do projeto</li></ul>                                                                                                                                                               |                 TBA                 |
> |             Líder de segurança             |                                                                                                                                                        <ul><li>Alimentar a fase de Descoberta em processos e designs de segurança</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de segurança durante a execução do projeto</li></ul>                                                                                                                                                        |                 TBA                 |
> |            Líder de telefonia             |                                                                                                                                                              <ul><li>Alimentar a fase de Descoberta em design de telefonia</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de telefonia durante a execução do projeto</li></ul>                                                                                                                                                              |                 TBA                 |
> |             Líder de desktop              |                                                                                                                                                          <ul><li>Alimentar a fase de Descoberta em clientes e processos de atualização</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de desktop durante a execução do projeto</li></ul>                                                                                                                                                          |                 TBA                 |
> |        Líder de suporte/suporte técnico         |                                                                                                                          <ul><li>Alimentar a fase de Descoberta em modelos de operação e suporte</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Participar no planejamento do modelo de suporte</li><li>Coordena o trabalho das equipes/recursos de suporte durante a execução do projeto</li></ul>                                                                                                                          |                 TBA                 |
> |     Representantes das unidades de negócios     |                                                                                                                                                                                                      <ul><li>Contribuir com guias e materiais de adoção baseados no usuário final</li><li>Contribuir e analisar casos de uso comercial</li></ul>                                                                                                                                                                                                      |                 TBA                 |
> |            Líder de implantação            |                                                                                                                                                           <ul><li>Garantir que os pré-requisitos de implantação sejam atendidos</li><li>Envolver os recursos do cliente para as atividades da fase de preparação e implantação</li><li>Participar de reuniões para analisar o status de preparação e implantação</li></ul>                                                                                                                                                            |                 TBA                 |
> |               Administradores de TI               |                                                                                                                                                                                                                           <ul><li>Profissionais de TI responsáveis pela assistência no planejamento e execução de testes</li></ul>                                                                                                                                                                                                                            |                 TBA                 |
> |             Proprietário do serviço             |                                                                                                                                                                                                  <ul><li>Responsável pela operação do serviço de Audioconferência</li><li>Proprietário do serviço de Audioconferência</li></ul>                                                                                                                                                                                                   |                 TBA                 |
> |           Defensores da qualidade           |                                                                                                      <ul><li>Direciona qualidade, confiabilidade e feedback dos usuários</li><li>Identifica as tendências de qualidade e direciona remediação com as respectivas equipes</li><li>Reporta-se ao comitê de direção e de volta à liderança</li><li>Reporta-se sobre qualidade, confiabilidade e sentimento dos usuários através do Rate My Call e Net Promoter Score</li></ul>                                                                                                       |                 TBA                 |

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Defina os objetivos e os resultados principais, os principais indicadores de sucesso e os riscos
--------------------------------------------------------------------

Com as partes envolvidas do projeto reunidas, os casos de uso comercial, o escopo organizacional e os cronogramas do projeto podem ser traduzidos em objetivos e resultados principais (OKRs), e as medições de sucesso do projeto podem ser definidas em uma lista de principais indicadores de sucesso (KSIs).

A participação das partes envolvidas do projeto na definição dos OKRs e KSIs assegurará o senso de propriedade e eles serão alinhados aos requisitos comerciais das empresas.

Os OKRs contêm a lista dos objetivos estabelecidos no início do projeto, com os principais resultados mensuráveis definidos em uma base trimestral. Os principais resultados são avaliados mensalmente para monitorar o status geral do projeto e, com base no progresso, podem ser feitos ajustes nos planos trimestrais conforme a necessidade.

> [!TIP]
> Consulte a seguir exemplos de OKRs relevantes à implementação da Audioconferência:
> <br>
> 
> **Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
> 
> |Objetivos  |Resultados principais  |A fazer  |
> |---------|---------|---------|
> |Implantar Audioconferência no Teams até o final do ano fiscal de 2018|1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018|2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

Os KSIs mensuram a qualidade e o sucesso dos principais resultados e complementam a natureza binária dos OKRs (alcançados ou não alcançados) ao detalhar os bons e/ou maus resultados. Ao definir os KSIs, recomendamos aproveitar os critérios “específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo” ou SMART.

> [!TIP]
> Este é um exemplo de KSI relevante para esse projeto:
> 
> |Tipo  |Pergunta e critérios do KSI  |Como foi mensurado  |Critérios de sucesso  |Mensurado  |Responsável  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adoção|A qualidade da chamada é igual ou melhor que a solução anterior|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Esquipe de Tecnologia da Informação|
> |Uso/adoção|O Microsoft Teams facilitou o processo de comunicação|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/adoção|Os usuários usam a solução ativamente|Relatórios do Office 365, Painel de Qualidade da Chamada|80% dos usuários são usuários ativos diariamente|Diariamente|Equipe de gerenciamento de mudanças|
> |Uso/qualidade|A porcentagem de chamadas/conferências de má qualidade deve ser mínima|Painel de Qualidade da Chamada|< 5% de chamadas de má qualidade por mês|Diariamente|Esquipe de Tecnologia da Informação|
> |Uso/suporte|Eu sei como obter suporte técnico|Pesquisa|90% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/suporte|Estou satisfeito com a qualidade do suporte técnico|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após cada incidente|Esquipe de Tecnologia da Informação|
> |Financeiro|Redução dos minutos de conferência herdados|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Como parte desse exercício, você precisa identificar os riscos de negócios e definir um plano de mitigação para cada um dos riscos identificados. Essas informações podem ser coletadas em um plano de riscos.

> [!TIP]
> Seu plano de riscos pode ser documentado como no exemplo a seguir:
> 
> |Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
> |---------|---------|---------|---------|---------|
> |A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas incorporadas, separar o OKR com o processo próprio (Concepção, Integração, Geração de valor)</li><li>Não inclui-los nos OKRs existentes</li></ul>|
> |A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte à portabilidade dos números de telefone antes (ou seja, registros do atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</li><li>Ajustar o cronograma do projeto para absorver o tempo de entrega dos resultados da execução da portabilidade dos números de telefone</li><li>Comunicar o uso de novos números de conferência de discagem para os participantes externos</li></ul>|
> |Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar o Teams como uma plataforma de colaboração e comunicação moderna, execute a avaliação da prontidão da rede para sites no âmbito do projeto</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Avalie o ambiente e avalie a prontidão para adoção
--------------------------------------------------

Para alcançar os OKRs pretendidos, você pode precisar definir a arquitetura de alto nível da solução. É necessária uma pesquisa do ambiente para avaliar todos os aspectos relacionados à infraestrutura de TI e telefonia, redes e operações.

Todos os assuntos relacionados a computação de usuário final, como a avaliação de prontidão dos computadores pessoais e dispositivos móveis para suportar os casos de uso comercial de Audioconferência, desde os requisitos de hardware até os requisitos de software, serão incluídos como parte da pesquisa do ambiente.

A pesquisa do ambiente também esclarece se há necessidade de [transferir os números de telefone para a Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365). Isso ajudará a sua organização a ajustar adequadamente o plano do projeto e preparar as informações necessárias para a portabilidade dos números. Você pode fazer a pesquisa do ambiente utilizado o seguinte [questionário](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

A pesquisa do ambiente deve incluir avaliação da prontidão da rede para garantir que a rede esteja pronta para suportar a implementação do serviço de Audioconferência.

É possível determinar se a rede está preparada para dar suporte à Audioconferência utilizando as informações captadas pela pesquisa do ambiente (como detalhes de conectividade com a Internet e topologia da WAN, links de sites e largura de banda disponível) e os dados de análise pessoal (que podem ser convertidos em uso esperado de cada carga de trabalho) na ferramenta [My Advisor Network Planning](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Para confirmar a prontidão da rede, pode ser feita uma simulação de tráfego de mídia em tempo real usando as soluções fornecidas pela [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) ou pelos [parceiros das ferramentas de Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners).

Os resultados da avaliação da prontidão da rede darão uma ideia mais clara da otimização ou da remediação necessária da rede para o sucesso da implementação da Audioconferência.

A prontidão para a adoção pode ser avaliada através da execução de análise pessoal para criar uma lista de pessoas na organização que podem ser direcionadas para a implementação do serviço de Audioconferência. A análise pessoal inclui a identificação de periféricos adicionais ou dispositivos necessários para atingir os resultados comerciais pretendidos.

Fara fazer a análise pessoal, você pode conduzir um workshop envolvendo as partes envolvidas no projeto, utilizando o [deck de workshop Alinhamento Pessoal](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) e a [Matriz de características pessoais](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). O resultado do workshop de análise pessoal pode ser resumido em um relatório usando o modelo de [Relatório de análise pessoal](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Ao passo que os exemplos de Questionário de Descoberta e Análise Pessoal foram inicialmente escritos para o Skype for Business Online, a maioria do conteúdo é relevante para o Teams. Fique à vontade para modificar e remover itens que não são relevantes para os objetivos do seu projeto.

Você pode identificar riscos técnicos como parte da avaliação ambiental e da avaliação de prontidão para adoção, e desenvolver um plano de mitigação para cada risco identificado. Essas informações devem ser incorporadas como parte do plano de risco.

<a name="map-operational-roles"></a>Mapear funções operacionais
---------------------

O planejamento das operações e a identificação das equipes que operarão o serviço de Audioconferência é um passo importante, pois as operações devem ser iniciadas quando os primeiros usuários piloto estiverem habilitados. Cada uma das equipes identificadas precisa avaliar e chegar a um acordo quanto às tarefas e responsabilidades identificadas, e iniciar a preparação para operar o serviço de Audioconferência. A preparação pode incluir treinamentos e prontidão, pessoal adicional ou a certeza de que os provedores externos estão configurados para entregar o serviço.

> [!TIP]
> Segue um exemplo de um modelo para documentar o resultado do exercício de mapeamento de funções operacionais que você realizou para dar suporte a esse projeto:
> 
> |Função operacional  |Descrição  |Equipe  |Detalhes de contato  |
> |---------|---------|---------|---------|
> |Proprietário do serviço|Proprietário do serviço, interface com as divisões da empresa, estratégia|TBA|TBA|
> |Operações de Audioconferência|Operações diárias, migração/adição/alteração de contas de usuários e dispositivos, monitoramento|TBA|TBA|
> |Administração de locatários|Alterar configuração de todos os locatários, habilitar novos recursos|TBA|TBA|
> |Central de atendimento|Interface para os usuários finais obterem suporte|TBA|TBA|
> |Operações de rede|Executa LAN, WAN, Wi-Fi e acesso à internet|TBA|TBA|
> |Cliente e equipe de pontos de extremidade|Gerenciar implantações de desktop|TBA|TBA|
> |Operações de identidade|Gerenciar infraestrutura de identidade (AD, ADFS, Azure AD)|TBA|TBA|
> |Gerenciamento de mudanças/adoção|Gerenciar conscientização, treinamentos e adoção da solução|TBA|TBA|
> |Operações do Exchange|Gerenciar o ambiente do Exchange|TBA|TBA|

Para facilitar um mapeamento mais detalhado das funções operacionais, incluindo as tarefas associadas a cada uma das funções operacionais, você pode usar o [Pasta de trabalho de mapeamento de funções operacionais](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) para coletar os detalhes que esclarecerão as funções e responsabilidades para suportar o serviço de Audioconferência.

<a name="document-success-plan"></a>Documentar plano de sucesso
---------------------

O plano de sucesso é a documentação criada na fase de Concepção, que consiste em caso de negócios, prontidão de serviço, plano de adoção e plano operacional.

O plano de sucesso fornecerá à equipe do projeto, que pode incluir FastTrack ou parceiro de implantação, informações suficientes para atingir os objetivos do serviço de Audioconferência da organização.

No geral, um plano de sucesso deve conter as seguintes seções principais:

-   Caso de negócios
-   Prontidão de serviço
-   Plano de adoção
-   Plano operacional

### <a name="business-case"></a>Caso de negócios

Casos de uso comercial, partes envolvidas, OKRs e KSIs, riscos e cronogramas do projeto geralmente compõem a maior parte das informações necessárias para um caso de negócios. Você precisa documentá-los como parte do plano de sucesso.

### <a name="service-readiness"></a>Prontidão de serviço

A avaliação do ambiente fornece as informações iniciais necessárias para determinar a prontidão técnica para a organização implementar a Audioconferência.

Aqui incluído está o plano para abordar as áreas que precisam de remediação descobertas através da avaliação do ambiente. Você precisa incluir a avaliação de prontidão de serviço e o plano de remediação como parte do plano de sucesso.

### <a name="adoption-plan"></a>Plano de adoção

Após a avaliação de prontidão para adoção, deve ser feito um planejamento detalhado adicional para que a equipe do projeto estabeleça um conjunto abrangente de planos de comunicação, plano de treinamento e atividades de adoção pré-lançamento, no lançamento e pós-lançamento.

Os recursos para dar suporte às atividades de adoção, como folhetos, e-mails de boas-vindas e materiais de treinamento, são identificados nesta etapa, juntamente com as personalizações necessárias para atender aos requisitos organizacionais.

Os modelos para as atividades de adoção estão disponíveis [aqui](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plano operacional

O exercício de mapeamento de funções operacionais estabelecerá as funções, as responsabilidades,e as equipes designadas a cada função operacional para dar suporte à implementação da Audioconferência.

Você precisa inserir isso e incluir o plano operacional como parte do plano de sucesso para garantir a prontidão operacional da solução.

<br>
Planejamento técnico da Audioconferência
-----------------------------------------
<a name="technical-planning-for-audio-conferencing"></a> Para planejar a implementação técnica de conferência de áudio, uma série de decisões que deve ser feita antes do tempo melhor preparar sua organização para implementar uma solução que atenda aos requisitos de negócios. Essas decisões serão documentadas no plano de implementação técnica.

## <a name="availability-of-audio-conferencing"></a>Disponibilidade da Audioconferência

A Audioconferência está disponível nestes [países e regiões](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais, para que a Audioconferência esteja disponível para organizações multinacionais, o contrato de assinaturas do Office 365 deve ser obtido de países e regiões cobertos pelo serviço de Audioconferência ou de onde o serviço de Audioconferência está disponível comercialmente.

Depois de confirmar a elegibilidade da sua organização para obter o serviço de Audioconferência, com base na lista de países e regiões disponíveis, compile a lista dos locais de usuários ou escritórios onde o serviço de Audioconferência será implementado.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais locais de usuários ou escritórios implementarão o serviço de Audioconferência</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os locais de usuários ou escritórios que implementarão o serviço de Audioconferência</li></ul>|

> [!TIP]
> Segue um exemplo de lista de habilitação de locais do Sistema de Telefonia com Planos de Chamadas:
> 
> |Escritório   |Localização |Serviço de Conferência PSTN  |
> |---------|---------|---------|
> |One Epping Road|Austrália|Audioconferência|
> |100 Alma Road|Hong Kong SAR|Conferência PSTN herdada|
> |One Marina Boulevard|Cingapura|Audioconferência|
> |32 London Bridge Street|Reino Unido|Audioconferência|
> |39 quai du Président Roosevelt|França|Audioconferência|

## <a name="licensing-for-audio-conferencing"></a>Licença para a Audioconferência

A [licença da Audioconferência](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) está disponível como parte dos planos de assinatura do Office 365 E5 ou como um complemento aos planos de assinatura do Office 365 E1 ou Office 365 E3.

> [!NOTE]
> A conferência PSTN ou por discagem no Teams não suporta Provedores de Audioconferência<sup></sup> de terceiros (ACPs). <br>Se você já usa a Conferência PSTN do Skype for Business hoje, você pode aproveitar a Audioconferência no Teams imediatamente.

Para fornecer números de telefone gratuitos de ponte de conferência e para suportar discagem de conferência para números de telefone internacionais, você precisa configurar [Créditos de Comunicação](what-are-communications-credits.md) para a sua organização.

> [!IMPORTANT]
> Alguns países são atendidos apenas por números de telefone gratuitos para ponte de conferência, e nesse caso, o uso de Créditos de Comunicação é um requisito obrigatório para ter suporte de acesso a esses países.

A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados. Os valores de fundos recomendados podem ser consultados no artigo [Créditos de Comunicação](what-are-communications-credits.md).

Se a sua organização optar por usar a recarga automática, uma recomendação sobre o gatilho (menor valor de fundos) também está incluída no artigo [Créditos de Comunicação](what-are-communications-credits.md). O valor da recarga automática deve ser determinado pelo uso real. O uso de Créditos de Comunicação deve ser monitorado ao longo do tempo e o valor da recarga precisa ser ajustado conforme a necessidade.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se a sua organização ainda não tiver adquirido a licença necessária para a Audioconferência, decida se as licenças da Audioconferência serão adquiridas ampliando as assinaturas existentes do Office 365 ou adquirindo complementos de Audioconferência.</li><li>Decida se os Créditos de Comunicação serão obrigatórios para a implementação da Audioconferência. Em caso positivo, decida o valor inicial de fundos a serem comprados. Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documentar os usuários que receberão a licença da Audioconferência</li><li>Documente o plano de Créditos de Comunicação (valor inicial, valor do gatilho, valor da recarga automática)</li></ul>|

> [!TIP]
> Você pode documentar a lista de atribuição de licenças para usuários da Audioconferência usando este exemplo:
> 
> |Usuário  |Escritório  |Licença do Office 365  |
> |---------|---------|---------|
> |Adele Vance|One Epping Road|Office 365 E5|
> |Alex Wilber|One Epping Road|Office 365 E3, complemento de Audioconferência|
> |Ben Walters|One Epping Road|Office 365 E3, complemento de Audioconferência|
> |Christie Cline|One Marina Boulevard|Office 365 E3, complemento de Audioconferência|
> |Debra Berger|One Marina Boulevard|Office 365 E5|
> |Lee Gu|One Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Pradeep Gupta|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferência|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferência|

<br>
> [!TIP]
> Os números do planejamento de seus Créditos de Comunicação podem ser documentados da seguinte maneira:
> |         |         |
> |---------|---------|
> |Valor inicial|US$ 1.000|
> |Valor do gatilho|US$ 400|
> |Valor da recarga automática|TBA|
> 

## <a name="conference-bridge-phone-numbers"></a>Números de telefone de ponte de conferência

O serviço de Audioconferência do Office 365 inclui:

-   Vários tipos de números de telefone de ponte de conferência (pagos e gratuitos)
-   Várias categorias de número de telefone (exclusivo e compartilhado)
-   Suporte de vários idiomas para a ponte de conferência (primária e secundária)
-   Um número de telefone padrão para o locatário.

A descrição completa das funcionalidades incluídas pode ser consultada em [Configurar a Audioconferência para o Skype for Business e o Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) e em [Números de telefone e Audioconferência](phone-numbers-for-audio-conferencing-in-teams.md).

> [!NOTE]
> Os números de telefone exclusivos da ponte de conferência são contados em relação ao limite de números de telefone que podem ser adquiridos por locatário com base no número de licenças aplicáveis, conforme descrito em [Obter números de telefone para o serviço Skype for Business e Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers). Os números de telefone gratuitos da ponte de conferência não precisam de Créditos de Comunicação.

Se houver números de telefone existentes da ponte de conferência que precisem ser transferidos para o serviço de Audioconferência, presumindo que estejam cumprindo os requisitos específicos do país, os números de telefone da ponte de conferência existentes poderão ser transferidos para a Microsoft.

> [!NOTE]
> A complexidade da transferência de números de telefone para a Microsoft varia muito com base nos países ou regiões, operadoras, o número de circuitos envolvidos e vários outros fatores. Para planejar a portabilidade dos números de telefone, consulte o [Guia de portabilidade de números](https://go.microsoft.com/fwlink/?linkid=859011).

Mais detalhes sobre a transferência de números de telefone para o serviço de Audioconferência estão disponíveis em [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir se a organização exigirá números de telefone exclusivos da ponte de conferência</li><li>Decidir como os números de telefone exclusivos da ponte da conferência serão obtidos para locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência (obter da Microsoft ou transferir os números de telefone existentes)</li><li>Se você optar por obter da Microsoft, decidir o método para obter números de telefone (envio de formulários ou automatizado) para os locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência</li><li>Decidir as preferências de idioma a ser configuradas para naca números de telefone de ponte de conferência</li><li>Decidir o número de telefone de ponte de conferência padrão do locatário</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documentar o plano mestre para a aquisição de números de telefone, detalhando como os números de telefone serão obtidos para cada um dos locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência.</li><li>Se aplicável, preencha <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">o formulário de solicitação de novo número de telefone</a>, um formulário para cada local ou escritório</li><li>Se você optar por transferir números de telefone existentes, confira o <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guia de Portabilidade de Números</a> para planejar a transferência e ajustar o cronograma de implementação da Audioconferência de maneira apropriada</li><li>Documentar as configurações detalhadas do número de telefone da ponte de conferência (números de telefone exclusivos e compartilhados da ponte de conferência, preferências de idioma para cada número exclusivo de telefone da ponte de conferência, número de telefone da ponte de conferência padrão do locatário)</li></ul>|

> [!TIP]
> Veja a seguir o exemplo de um modelo para capturar detalhes da ponte de conferência:
> 
> |Escritório   |Aquisição do número da ponte e Tipo da ponte |Número da ponte  |Idioma da ponte|
> |---------|---------|---------|---------|
> |One Epping Road|Adquirir novo, exclusivo|TBA|Inglês (Austrália)|
> |One Marina Boulevard|Adquirir novo, compartilhado|TBA|Inglês (Estados Unidos); Chinês (Simplificado, PRC)|
> |32 London Bridge Street|Porta existente, exclusiva|+44 20 7946 0001|Inglês (Reino Unido)|
> |39 quai du Président Roosevelt|Adquirir novo, exclusivo|TBA|Francês (França), Inglês (Reino Unido)|

## <a name="conference-bridge-settings"></a>Configurações de ponte de conferência

As opções de configuração da experiência de entrar em uma reunião de Audioconferência em toda a organização (notificação de entrada e saída e gravação de nome do chamador), o comprimento do PIN do organizador da reunião e a notificação por e-mail estão disponíveis para adaptar melhor a experiência do usuário final.

-   As notificações de entrada e saída de reuniões estão disponíveis na forma de nome, número de telefone e tons registrados.
-   O comprimento do PIN pode ter de 4 a 12 dígitos, com um PIN de 5 dígitos como padrão.
-   Os e-mails de notificação após a habilitação da licença de Audioconferência ou qualquer outra alteração conduzida pelo administrador estão habilitados por padrão. Você pode desabilitar esse recurso e assumir o controle das comunicações dos usuários finais da sua organização.

Para os usuários aos quais tenha sido atribuída uma licença de Audioconferência, os números chamada pagos e gratuitos padrão, mostrados nas coordenadas de Audioconferência, podem ser configurados para uso:

-   no padrão em nível de locatário ou
-   em números de telefone de ponte de conferência atribuídos automaticamente ou
-   em números de telefone de ponte de conferência definidos manualmente para cada usuário.

Os números de telefone da ponte de conferência específicos do usuário costumam ser úteis em organizações nacionais ou internacionais, onde os usuários são distribuídos e precisam fornecer números locais como números de telefone da ponte de conferência padrão nos convites de reunião.

Os participantes que entram de diferentes cidades ou do exterior podem procurar números adicionais configurados no nível do locatário, mas esses números não aparecem diretamente nos convites de reunião. Os convites de reunião contêm um link que levará os participantes à página de números de discagem da conferência do Teams para que eles procurem os números de telefone da ponte de conferência mais próximos do seu local que estejam disponíveis.

Você também pode configurar como os autores de chamada não autenticados são tratados por cada organizador de reunião individual para exigir que o organizador da reunião inicie a reunião antes que os autores de chamada não autenticados sejam admitidos ou para permitir que os autores de chamada não autenticados iniciem uma reunião.

Estão disponíveis configurações adicionais que podem ser aplicadas para cada usuário para controlar o uso de números de telefone gratuitos de ponte de conferência e discagem de uma conferência.

> [!NOTE]
> Esses controles relacionados a custo estão atualmente disponíveis somente para clientes da prévia. Você pode registrar sua organização no programa de visualização de [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Com esses controles, você pode decidir se os organizadores da reunião podem fornecer números de telefone gratuitos de ponte de conferência para reuniões organizadas por eles, ou para controlar se os participantes podem discar das reuniões organizadas por eles. O nível de controle de discagem vai da exclusão da permissão de discagem, permitindo discar apenas para números domésticos, até a permissão de discagem para números domésticos e internacionais.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir se a organização exigirá notificações de entrada e saída e, em caso afirmativo, o tipo de notificação a ser implementada (tons, número de telefone ou nome registrado)</li><li>Decidir o tamanho do PIN da Audioconferência que atende às exigências de segurança da organização</li><li>Decidir se a organização deseja assumir o controle das comunicações do usuário final relacionadas ao serviço de Audioconferência</li><li>Decidir os números de telefone da ponte da conferência que devem ser atribuídos a cada organizador de reunião</li><li>Decidir se alguns organizadores de reunião exigirão o recurso de usar números de telefone gratuitos de ponte de conferência para as suas reuniões</li><li>Decidir se alguns organizadores de reunião precisarão permitir que autores de chamadas não autenticados iniciem uma reunião</li><li>Decidir se alguns organizadores de reunião precisarão que a discagem de saída da conferência seja controlada</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documentar detalhadamente as configurações de ponte de conferência (notificações de entrada e saída, tamanho do PIN, notificação por email de alteração do configurações)</li><li>Documentar os números de telefone de ponte de conferência que serão atribuídos a cada organizador de reunião e a configuração correspondente para controlar a política de autores de chamadas não autenticados e os controles de discagem de saída e de chamada gratuita</li></ul>|

> [!TIP]
> As configurações de ponte de conferência podem ser documentadas da seguinte maneira:
> 
> |         |         |
> |---------|---------|
> |Permitir notificações de entrada e saída de reuniões|Habilitado|
> |Tipo de anúncio de entrada/saída|Tons|
> |Solicitar que os autores de chamadas registrem seus nomes antes de ingressar na reunião|Desabilitado|
> |Tamanho do PIN|5|
> |Enviar emails automaticamente para os usuários quando suas configurações de discagem forem alteradas|Desabilitado|

<br>

> [!TIP]
> Você pode documentar a lista de atribuição de configurações de ponte de conferência de usuários da Audioconferência usando este exemplo:
>
> |Usuário  |Escritório  |Número de chamada padrão  |Número de chamada gratuita padrão  |Permitir chamada gratuita  |Autores de chamada não autenticados ignoram o lobby  |Discagem de saída de conferência  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|TBA|TBA|Sim|Habilitado|Doméstico e internacional|
> |Alex Wilber|One Epping Road|TBA|TBA|Não|Desabilitado|Não permitido|
> |Ben Walters|One Epping Road|TBA|TBA|Não|Desabilitado|Não permitido|
> |Christie Cline|One Marina Boulevard|TBA|TBA|Sim|Desabilitado|Doméstico|
> |Debra Berger|One Marina Boulevard|TBA|TBA|Sim|Habilitado|Doméstico|
> |Lee Gu|One Marina Boulevard|TBA|TBA|Sim|Habilitado|Doméstico|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Habilitado|Não permitido|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Desabilitado|Não permitido|
> |Pradeep Gupta|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Desabilitado|Não permitido|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Sim|Habilitado|Doméstico e internacional|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|

## <a name="dial-plans"></a>Planos de discagem

O [Plano de Discagem](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) do recurso do Sistema de Telefonia do Office 365 é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente o formato[E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para autorização e roteamento de chamadas. O serviço de Audioconferência aproveita os mesmos recursos usados pelo Sistema de Telefonia para converter números de telefone discados em cenários de discagem de saída de conferência.

Um plano de discagem permite que os usuários disquem números de telefone da forma como estão acostumados, como omitir o código de área para chamadas locais, omitir o código de país para chamadas domésticas ou mesmo usar atalhos de discagem ao fazer uma discagem de saída de conferência.

Dentro do recurso Sistema de Telefonia do Office 365, existem dois tipos de planos de discagem:

-   **Plano de discagem para serviço**. Esse é o plano de discagem padrão, é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.
-   **Plano de discagem para locatários**. Esse é um plano de discagem personalizável em um locatário e é dividido em mais dois tipos:
    -   **Plano de discagem para locatário global** – o plano de discagem se aplica para todos os usuários do locatário.
    -   **Plano de discagem para locatário usuário** – o plano de discagem se aplica apenas a usuários específicos.

> [!NOTE]
> Confira mais detalhes e exemplos na documentação [O que são os planos de discagem?](what-are-dial-plans.md)

O plano de discagem efetivo atribuído aos usuários é a combinação do plano de discagem para serviço (com base no local de uso do Office 365 do usuário) e do plano de discagem para locatários (que pode ser o plano de discagem para locatário global ou o plano de discagem para locatário usuário).

![A tabela mostra três combinações de planos de discagem para locatários e serviços.](media/audio_conferencing_image8.png)

Há um máximo de 25 regras de normalização em cada plano de discagem para locatários e, portanto, a duplicação das regras de normalização já disponíveis como parte do plano de discagem para serviço precisa ser evitada.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a sua organização requer planos de discagem personalizados (requisitos de negócios, requisitos de adoção etc.).</li><li>Se aplicável, decida o escopo do plano de discagem de locatário (locatário global ou locatário usuário) para dar suporte aos requisitos dos planos de discagem personalizados</li><li>Se aplicável, decidir os planos de discagem de locatários que serão criados para oferecer suporte a locais de usuários ou escritórios no escopo de implementação da Audioconferência</li><li>Se aplicável, decida qual usuário requer um plano de discagem personalizado e o plano de discagem de locatário que deve ser atribuído a cada usuário</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documentar os planos de discagem personalizados e as regras de normalização associadas que devem ser configuradas como parte da implementação da Audioconferência</li><li>Documente os usuários aos quais deve ser atribuído um plano de discagem personalizado e o plano de discagem de locatário a ser atribuído a cada usuário</li></ul>|

> [!TIP]
> Se aplicável para o seu projeto, você pode usar o modelo a seguir para documentar das configurações dos planos de discagem de locatário:
> 
> |Nome do plano de discagem de locatário<br>_Descrição_  |Nome das regras de normalização<br>_Descrição_  |Padrão<br>Conversão<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, AU Dial Plan_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para o escritório de One Epping Road, North Ryde, NSW, Austrália_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalização do número local para NSW, Austrália_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalização de número gratuito na Austrália_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalização de número de serviço na Austrália_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore, SG Dial Plan_|**SG-OMB-Internal**<br>_Número interno (x8000 – x8999) para o escritório OMB, Cingapura_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalização de número gratuito em Cingapura_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalização de número de serviço em Cingapura_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan_|**FR-39qdPR-Internal**<br>_Número interno (x7000 – x7999) para o escritório de 39 quai du Président Roosevelt, Issy-les-Moulineaux, França_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalização de número gratuito na França_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalização de número de serviço na França_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> O modelo de exemplo a seguir pode ser utilizado para documentar atribuições de planos de discagem para dar suporte ao seu projeto:
>
> |Usuário  |Escritório  |Tipo do plano de discagem  |Nome do plano de discagem  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Lidia Holloway|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Pradeep Gupta|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|

## <a name="microsoft-teams-configurations"></a>Configurações do Microsoft Teams

O suporte para Audioconferência está disponível para reuniões ad hoc e agendadas. Para reuniões agendadas, as configurações em nível de locatário que regem o agendamento de reuniões (reuniões privadas e de canal) devem estar habilitadas.

> [!NOTE]
> No momento, se sua organização tiver exigências de conformidade para garantir que todas as discussões nas reuniões sejam detectáveis, é necessário desabilitar as reuniões privadas se o organizador tiver uma caixa de correio no Exchange.<br>
> Em outro caso de uso, se todas as reuniões da organização tiverem que permanecer visíveis apenas **para as partes convidadas**, recomendamos que você desabilite a possibilidade de agendar reuniões nos **canais** para evitar a divulgação das informações da reunião para as partes que não foram convidadas.

As configurações, disponíveis como configurações em nível de locatário, são aplicáveis para todos os usuários da organização e afetarão todas as reuniões agendadas no Teams, não especificamente as reuniões Teams **com** Audioconferência.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir se a organização precisa ativar ou desativar o agendamento de reuniões privadas</li><li>Decidir se a organização precisa ativar ou desativar o agendamento de reuniões de canal</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documentar as configurações de agendamento de reuniões do Microsoft Teams</li></ul>|

> [!TIP]
> As configurações de reuniões do Microsoft Teams podem ser documentadas da seguinte maneira:
> 
> |         |         |
> |---------|---------|
> |Permitir o agendamento de reuniões privadas|Habilitado|
> |Permitir o agendamento de reuniões de canal|Desabilitado|

## <a name="document-technical-implementation-plan"></a>Documentar o plano de implementação técnica

Utilizar os pontos de decisão acima para documentar o seu plano de implementação técnica.
Esse plano de implementação técnica fornecerá à equipe do projeto, que pode incluir o FastTrack ou um parceiro de implantação, as informações necessárias para executar a integração técnica para a implementação da Audioconferência.

No geral, um plano de implementação técnica deve conter as seguintes seções principais:

-   Lista de habilitação do site do serviço de Audioconferência

-   Lista de atribuição de licenças para organizadores de reunião de Audioconferência

-   Número de planejamento de Créditos de Comunicação

-   Detalhes de ponte de conferência

-   Configurações de ponte de conferência

-   Atribuições das configurações de ponte de conferência

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

-   Configurações de reuniões Microsoft Teams

<br>
Com a conclusão do plano de sucesso e do plano de implementação técnica, agora você está pronto para conduzir a sua organização para as próximas etapas da jornada do cliente do Office 365.

<br>
Integração =======

*Em breve.*

<br>
Geração de valor ===========

*Em breve.*

<br>
## <a name="see-also"></a>Consulte também

[Configurar a Audioconferência para o Skype for Business e o Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
