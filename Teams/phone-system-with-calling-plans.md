---
title: Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Orientações práticas para planejar, implantar e gerenciar o Sistema de Telefonia com Planos de Chamadas no Microsoft Teams usando a estrutura Concepção (planejamento), Integração (fornecimento), Geração de valor (operação).
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: 2ce4d09113cc75381379fa6f9481eca2ae27c2ea
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23853651"
---
<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a>Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams
=========================================================================

O Sistema de Telefonia é um recurso do Office 365 que permite gerenciar o encaminhamento de chamadas, políticas e o provisionamento de usuários. Isso inclui o sistema de gerenciamento de chamadas telefônicas, o encaminhamento e o controle de chamadas.

Os Planos de Chamadas do Office 365 são um serviço complementar ao recurso Sistema de Telefonia, fornecido pelo Microsoft Teams e pelo Skype for Business Online. Os Planos de Chamadas fornecem às pessoas de sua empresa um número de telefone principal e permite que façam e recebam chamadas telefônicas fora da organização, pela PSTN (Rede Telefônica Pública Comutada).

Para saber mais, leia [Isto é o que você obtém com o Sistema de Telefonia no Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) e [O que são os Planos de Chamadas no Office 365?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)

Estas orientações práticas o direcionam pela estrutura da jornada do cliente do Office 365 FastTrack e suas três fases, Concepção, Integração e Geração de valor, para ajudar no planejamento, na entrega e na operação de uma implementação bem-sucedida do Sistema de Telefonia com Planos de Chamadas.

> [!TIP]
> Nessas orientações práticas, fornecemos exemplos de resultados de cada atividade e discussão importante. Os exemplos contidos neste documento estão incluídos nos balões de DICAS e servem como um modelo que você pode reutilizar. Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.

Concepção <a name="Envision_PhoneSystemWithCallingPlans"> </a>
========

A fase de Concepção proporciona a base para a jornada do cliente do Office 365 e se aplica a todas as cargas de trabalho, incluindo o Sistema de Telefonia com Planos de Chamadas.

Nessa fase, os objetivos de negócios são estabelecidos com as partes envolvidas relevantes do projeto reunidas, para entregar:

-   Um plano de sucesso e de alto nível que tenha casos de uso comercial, as principais partes envolvidas, os objetivos e os resultados principais (OKRs), os principais indicadores de sucesso (KSIs), os riscos, a avaliação do ambiente, a prontidão para adoção e o plano operacional.

-   Um plano detalhado de implementação técnica do Sistema de Telefonia com Planos de Chamadas para alcançar o estado final desejado.

<a name="define-business-use-cases-for-phone-system-with-calling-plans"></a>Definir casos de uso comercial para o Sistema de Telefonia com Planos de Chamadas
-------------------------------------------------------------

Com o Sistema de Telefonia com Planos de Chamadas, as organizações podem modernizar seu local de trabalho, permitindo que os usuários façam chamadas telefônicas relacionadas aos negócios usando seus computadores e dispositivos móveis.

A modernização do local de trabalho pode fazer parte de uma implementação de trabalho baseada na atividade, na mudança do escritório, na renovação de aparelhos do escritório, na retirada de soluções de PBX (Central privada de comutação telefônica) herdadas, no término do contrato de um provedor de serviços de PSTN etc.

Nesta etapa, as principais partes envolvidas no projeto definirão os casos de uso comercial que dão suporte à implementação do Sistema de Telefonia com Planos de Chamadas.

Os casos de uso comercial servem para documentar os resultados comerciais esperados e mensuráveis, e devem incluir:

-   Descrição do processo comercial atual
-   Definição dos desafios com os processos comerciais existentes
-   Como a tecnologia pode ajudar a superar esses desafios
-   Os resultados comerciais esperados e mensuráveis, se esses desafios forem superados

> [!TIP]
> Segue um exemplo de caso de uso comercial concluído:
>|         |
>|---------|
>|**Descrição do processo comercial atual**<p>A configuração padrão dos espaços de trabalho do escritório da Contoso inclui um telefone em cada mesa. Cada funcionário receberá um número de telefone DID (discagem interna direta). Os telefones de mesa são conectados a um sistema de PBX e à PSTN via tronco SIP. Os funcionários podem fazer e receber chamadas telefônicas somente nos telefones de mesa atribuídos a eles.|
>|**Desafios com os processos comerciais existentes**<p>A análise de uso dos telefones de mesa mostra que apenas 10% deles são usados ativamente. O resto é configurado para encaminhar chamadas para celulares ou para tocar simultaneamente nos celulares. A manutenção do sistema de PBX existente e dos telefones de mesa associados representa 20% do custo mensal do serviço de telefonia.|
>|**Como a tecnologia pode superar esses desafios**<p>O Sistema de Telefonia com Planos de Chamadas permitirá que os computadores dos usuários finais recebam e façam chamadas telefônicas pela rede de dados, aproveitando o aplicativo nativo do Microsoft Teams, eliminando a necessidade de distribuir e manter telefones de mesa, e cria a oportunidade de desativar o sistema de PBX existente, pois o serviço telefônico pode ser entregue pela nuvem, na rede, sem depender do sistema telefônico tradicional.|
>|**Resultados comerciais esperados e mensuráveis**<p>A remoção de requisitos para manter e desativar os telefones de mesa e PBX herdados existentes gera uma redução de 20% nas despesas mensais com serviços telefônicos. O Sistema de Telefonia com Planos de Chamadas simplificará os espaços de trabalho, permitindo que a Contoso expanda suas operações com o estabelecimento de novos escritórios com custos iniciais de telefonia mínimos.|

Durante a fase de Concepção, além de definir os casos de uso comercial, você também precisa esclarecer estes itens:
- Escopo organizacional
- Cronogramas do projeto

<a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas
-------------------------

Os casos de uso comercial definidos na etapa anterior incluirão o escopo organizacional da implementação do Sistema de Telefonia com Planos de Chamadas. Usando isso como base, é possível preencher a matriz completa de partes envolvidas, incluindo as pessoas certas que devem ser engajadas no projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
>|Função  |Descrição  |Nome, informações de contato, localização  |
>|---------|---------|---------|
>|Patrocinador executivo do projeto|<ul><li>A autoridade e a responsabilidade final pelo projeto e pela entrega dos objetivos do projeto</li><li>Ajudar a solucionar problemas escalados pelo Líder do projeto</li><li>Comunicação do patrocinador internamente na empresa sobre os objetivos do projeto</li><li>Responsável pela tomada de decisões estratégicas</li><li>Responsável pela disponibilidade do orçamento e dos recursos necessários</li><li>Liderança da avaliação trimestral de negócios (QBR)</li><li>Aceitação e ajuda nos esforços da campanha de conscientização</li><li>Atuando como patrocinador do projeto de distribuição do programa</li></ul>|TBA|
>|Líder de projeto|<ul><li>Gerenciamento e liderança da equipe do projeto</li><li>Coordena os parceiros e as equipes de trabalho envolvidos no projeto</li><li>Responsável pela criação e pelo gerenciamento dos planos do projeto para atingir os principais resultados trimestrais</li><li>Solucionar problemas multifuncionais</li><li>Passar atualizações regulares aos patrocinadores do projeto</li><li>Incorporação dos aspectos de adoção em todo o plano do projeto</li><li>Liderança das avaliações mensais de negócios e operações (MBR), contribuindo com as avaliações trimestrais de negócios</li></ul>|TBA|
>|Líder/arquiteto de colaboração|<ul><li>Responsável pela execução da estratégia de colaboração definida pelos executivos da empresa</li><li>Analisar e escolher produtos de colaboração para a empresa que atendam aos objetivos de negócios</li><li>Responsável pela concepção das operações dos produtos de colaboração</li><li>Define o modelo de operação e suporte</li><li>Contribuir com as avaliações trimestrais de negócios</li><ul>|TBA|
>|Consultor|<ul><li>Responsável pelos serviços de configuração</li><li>Contribui na arquitetura geral da solução</li></ul>|TBA|
>|Gerente de projetos|<ul><li>Desenvolvimento e manutenção do plano do projeto</li><li>Gerenciar os produtos finais do projeto de acordo com o plano do projeto e o orçamento</li><li>Registrar e gerenciar os problemas de projeto, incluindo o dimensionamento</li><li>Conduzir chamadas stand up semanais</li><li>Conectar-se e passar atualizações para patrocinadores executivos do projeto</li><li>Trabalhar com o Arquiteto para definir a abordagem de gerenciamento de mudanças e os planos de comunicação</li></ul>|TBA|
>|Especialista em adoção/gerenciamento de mudanças|<ul><li>Alimentar a fase de Descoberta em processos de treinamento e adoção</li><li>Participar do workshop de estratégia de adoção</li><li>Desenvolvimento e responsabilidade pela estratégia de adoção</li><li>Desenvolvimento e execução do plano de comunicação</li><li>Responsável por ministrar treinamentos aos usuários finais</li><li>Coletar feedback e conduzir pesquisas</li></ul>|TBA|
>|Líder de rede|<ul><li>Alimentar a fase de Descoberta em design de rede</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de rede durante a execução do projeto</li></ul>|TBA|
>|Líder de segurança|<ul><li>Alimentar a fase de Descoberta em processos e designs de segurança</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de segurança durante a execução do projeto</li></ul>|TBA|
>|Líder de telefonia|<ul><li>Alimentar a fase de Descoberta em design de telefonia</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de telefonia durante a execução do projeto</li></ul>|TBA|
>|Líder de desktop|<ul><li>Alimentar a fase de Descoberta em clientes e processos de atualização</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Coordena o trabalho da equipe de desktop durante a execução do projeto</li></ul>|TBA|
>|Líder de suporte/suporte técnico|<ul><li>Alimentar a fase de Descoberta em modelos de operação e suporte</li><li>Participar do planejamento durante o workshop de Concepção</li><li>Participar no planejamento do modelo de suporte</li><li>Coordena o trabalho das equipes/recursos de suporte durante a execução do projeto</li></ul>|TBA|
>|Representantes das unidades de negócios|<ul><li>Contribuir com guias e materiais de adoção baseados no usuário final</li><li>Contribuir e analisar casos de uso comercial</li></ul>|TBA|
>|Líder de implantação|<ul><li>Garantir que os pré-requisitos de implantação sejam atendidos</li><li>Envolver os recursos do cliente para as atividades da fase de preparação e implantação</li><li>Participar de reuniões para analisar o status de preparação e implantação</li></ul>|TBA|
>|Administradores de TI|<ul><li>Profissionais de TI responsáveis pela assistência no planejamento e execução de testes</li></ul>|TBA|
>|Proprietário do serviço|<ul><li>Responsável pela operação do serviço de Sistema de Telefonia com Planos de Chamadas</li><li>Proprietário do serviço de Sistema de Telefonia com Planos de Chamadas</li></ul>|TBA|
>|Defensores da qualidade|<ul><li>Direciona qualidade, confiabilidade e feedback dos usuários</li><li>Identifica as tendências de qualidade e direciona remediação com as respectivas equipes</li><li>Reporta-se ao comitê de direção e de volta à liderança</li><li>Reporta-se sobre qualidade, confiabilidade e sentimento dos usuários através do Rate My Call e Net Promoter Score</li></ul>|TBA|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Defina os objetivos e os resultados principais, os principais indicadores de sucesso e os riscos
--------------------------------------------------------------------

Com as partes envolvidas do projeto reunidas, os casos de uso comercial, o escopo organizacional e os cronogramas do projeto podem ser convertidos em OKRs (objetivos e resultados principais), e as medições de sucesso do projeto podem ser definidas em uma lista de KSIs (principais indicadores de sucesso).

A participação das partes envolvidas do projeto na definição dos OKRs e KSIs assegurará o senso de propriedade e eles serão alinhados aos requisitos comerciais das empresas.

Os OKRs contêm a lista dos objetivos estabelecidos no início do projeto, com os principais resultados mensuráveis definidos em uma base trimestral. Os principais resultados são avaliados mensalmente para monitorar o status geral do projeto e, com base no progresso, podem ser feitos ajustes nos planos trimestrais conforme a necessidade.

> [!TIP]
> Consulte a seguir exemplos de OKRs relevantes à implementação do Sistema de Telefonia com Planos de Chamadas:
><br>
>
>**Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
>|Objetivos  |Resultados principais  |A fazer  |
>|---------|---------|---------|
>|Implantar o Sistema de Telefonia com Planos de Chamadas nas filiais europeias até o final do ano fiscal de 2018|3º trimestre do ano fiscal de 2018: Implantar o Sistema de Telefonia com Planos de Chamadas no escritório de Londres|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
>|Encerrar o PBX herdado no escritório de Londres até o final do ano fiscal de 2018|4º trimestre do ano fiscal de 2018: Encerrar o PBX herdado no escritório de Londres|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

Os KSIs mensuram a qualidade e o sucesso dos principais resultados e complementam a natureza binária dos OKRs (alcançados ou não alcançados) ao detalhar os bons e/ou maus resultados. Ao definir os KSIs, recomendamos aproveitar os critérios “específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo” ou SMART.

> [!TIP]
> Este é um exemplo de KSI relevante para esse projeto:
>|Tipo  |Pergunta e critérios do KSI  |Como foi mensurado  |Critérios de sucesso  |Mensurado  |Responsável  |
>|---------|---------|---------|---------|---------|---------|
>|Uso/adoção|A qualidade da chamada é igual ou melhor que a solução anterior|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Esquipe de Tecnologia da Informação|
>|Uso/adoção|O Microsoft Teams facilitou o processo de comunicação|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
>|Uso/adoção|Os usuários usam a solução ativamente|Relatórios do Office 365, Painel de Qualidade da Chamada|80% dos usuários são usuários ativos diariamente|Diariamente|Equipe de gerenciamento de mudanças|
>|Uso/qualidade|A porcentagem de chamadas/conferências de má qualidade deve ser mínima|Painel de Qualidade da Chamada|< 5% de chamadas de má qualidade por mês|Diariamente|Esquipe de Tecnologia da Informação|
>|Uso/suporte|Eu sei como obter suporte técnico|Pesquisa|90% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
>|Uso/suporte|Estou satisfeito com a qualidade do suporte técnico|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após cada incidente|Esquipe de Tecnologia da Informação|
>|Financeiro|Redução das despeças mensais com serviços telefônicos|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Como parte desse exercício, você precisa identificar os riscos de negócios e definir um plano de mitigação para cada um dos riscos identificados. Inclua essas informações em um plano de riscos.

> [!TIP]
> Seu plano de riscos pode ser documentado como no exemplo a seguir:
>|Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
>|---------|---------|---------|---------|---------|
>|A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas incorporadas, separar o OKR com o processo próprio (Concepção, Integração, Geração de valor)</li><li>Não inclui-los nos OKRs existentes</li></ul>|
>|A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte à portabilidade dos números de telefone antes (ou seja, registros do atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</li><li>Ajustar o cronograma do projeto para absorver o tempo de entrega dos resultados da execução da portabilidade dos números de telefone</li><li>Usar números de telefone temporários com a manipulação de IDs de Chamadas</li></ul>|
>|Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar o Teams como uma plataforma de colaboração e comunicação moderna, execute a avaliação da prontidão da rede para sites no âmbito do projeto</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Avalie o ambiente e avalie a prontidão para adoção
--------------------------------------------------

Para alcançar os OKRs pretendidos, você pode precisar definir a arquitetura de alto nível da solução. É necessária uma pesquisa do ambiente para avaliar todos os aspectos relacionados à infraestrutura de TI e telefonia, redes e operações.

Todos os assuntos relacionados à computação de usuário final, como a avaliação de prontidão dos computadores pessoais e dispositivos móveis para dar suporte aos casos de uso comercial do Sistema de Telefonia com Planos de Chamadas, desde os requisitos de hardware até os requisitos de software, serão incluídos como parte da pesquisa do ambiente.

A pesquisa do ambiente também deve mostrar se há necessidade de [transferir os números de telefone para a Microsoft](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365). Isso ajudará a sua organização a ajustar adequadamente o plano do projeto e preparar as informações necessárias para a portabilidade dos números. Para realizar a pesquisa do ambiente, use o [Questionário de Descoberta](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

A pesquisa do ambiente deve incluir avaliação da prontidão da rede para garantir que a rede esteja pronta para dar suporte à implementação do Sistema de Telefonia com Planos de Chamadas.

A prontidão da rede para dar suporte ao Sistema de Telefonia com Planos de Chamadas pode ser determinada utilizando as informações coletadas através da pesquisa do ambiente (como detalhes da conectividade com a Internet e topologia da WAN, links de sites e largura de banda disponível) e dados de análise pessoal (que podem ser convertido em uso esperado de cada carga de trabalho) na ferramenta [My Advisor Network Planning](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Para confirmar a prontidão da rede, realize uma simulação de tráfego de mídia em tempo real usando estas soluções:
- Da Microsoft: [ferramenta de avaliação de rede do Skype for Business](https://www.microsoft.com/download/details.aspx?id=53885)
- De parceiros: [parceiros de ferramentas de Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners)

Os resultados da avaliação da prontidão da rede darão uma ideia mais clara da otimização ou da remediação necessária da rede para o sucesso da implementação do Sistema de Telefonia com Planos de Chamadas.

A prontidão para a adoção pode ser avaliada por meio de uma análise pessoal para criar uma lista de pessoas na organização que podem ser direcionadas para a implementação do Sistema de Telefonia com Planos de Chamadas. A análise pessoal inclui a identificação de periféricos adicionais ou dispositivos necessários para atingir os resultados comerciais pretendidos.

Fara fazer a análise pessoal, você pode conduzir um workshop envolvendo as partes envolvidas no projeto, utilizando o [deck de workshop Alinhamento Pessoal](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) e a [Matriz de características pessoais](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). O resultado do workshop de análise pessoal pode ser resumido em um relatório usando o modelo de [Relatório de análise pessoal](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Ao passo que os exemplos de Questionário de Descoberta e Análise Pessoal foram inicialmente escritos para o Skype for Business Online, a maioria do conteúdo é relevante para o Teams. Fique à vontade para modificar e remover itens que não são relevantes para os objetivos do seu projeto.

Você pode identificar riscos técnicos como parte da avaliação ambiental e da avaliação de prontidão para adoção, e desenvolver um plano de mitigação para cada risco identificado. Essas informações devem ser incorporadas como parte do plano de risco.

<a name="map-operational-roles"></a>Mapear funções operacionais
---------------------

O planejamento das operações e a identificação das equipes que operarão o serviço de Sistema de Telefonia com Planos de Chamadas é um passo importante, pois as operações devem ser iniciadas quando os primeiros usuários piloto estiverem habilitados. Cada uma das equipes identificadas precisa avaliar e chegar a um acordo quanto às tarefas e responsabilidades identificadas, e iniciar a preparação para operar o serviço de Sistema de Telefonia com Planos de Chamadas. A preparação pode incluir treinamentos e prontidão, pessoal adicional ou a certeza de que os provedores externos estão configurados para entregar o serviço.

> [!TIP]
> Segue um exemplo de um modelo para documentar o resultado do exercício de mapeamento de funções operacionais que você realizou para dar suporte a esse projeto:
>|Função operacional  |Descrição  |Equipe  |Detalhes de contato  |
>|---------|---------|---------|---------|
>|Proprietário do serviço|Proprietário do serviço, interface com as divisões da empresa, estratégia|TBA|TBA|
>|Operações do Sistema de Telefonia com Planos de Chamadas|Operações diárias, migração/adição/alteração de contas de usuários e dispositivos, monitoramento|TBA|TBA|
>|Administração de locatários|Alterar configuração de todos os locatários, habilitar novos recursos|TBA|TBA|
>|Central de atendimento|Interface para os usuários finais obterem suporte|TBA|TBA|
>|Operações de rede|Executa LAN, WAN, Wi-Fi e acesso à internet|TBA|TBA|
>|Cliente e equipe de pontos de extremidade|Gerenciar implantações de desktop|TBA|TBA|
>|Operações de identidade|Gerenciar infraestrutura de identidade (AD, ADFS, Azure AD)|TBA|TBA|
>|Gerenciamento de mudanças/adoção|Gerenciar conscientização, treinamentos e adoção da solução|TBA|TBA|
>|Operações do Exchange|Gerenciar o ambiente do Exchange|TBA|TBA|

Para facilitar um mapeamento mais detalhado das funções operacionais, incluindo as tarefas associadas a cada uma das funções operacionais, você pode usar a [Pasta de trabalho de mapeamento de funções operacionais](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) para coletar os detalhes que esclarecerão as funções e responsabilidades para dar suporte ao serviço de Sistema de Telefonia com Planos de Chamadas.

<a name="document-success-plan"></a>Documentar plano de sucesso
---------------------

O plano de sucesso é a documentação criada na fase de Concepção, que consiste em caso de negócios, prontidão de serviço, plano de adoção e plano operacional.

O plano de sucesso fornecerá à equipe do projeto, que pode incluir um parceiro de implantação ou FastTrack, informações suficientes para atingir os objetivos da organização com o Sistema de Telefonia com Planos de Chamadas.

No geral, um plano de sucesso deve conter as seguintes seções principais:

-   Caso de negócios
-   Prontidão de serviço
-   Plano de adoção
-   Plano operacional

### <a name="business-case"></a>Caso de negócios

Casos de uso comercial, partes envolvidas, OKRs e KSIs, riscos e cronogramas do projeto geralmente compõem a maior parte das informações necessárias para um caso de negócios. Você precisa documentá-los como parte do plano de sucesso.

### <a name="service-readiness"></a>Prontidão de serviço

A avaliação do ambiente fornece as informações iniciais necessárias para determinar a prontidão técnica para a organização implementar o Sistema de Telefonia com Planos de Chamadas.

Aqui incluído está o plano para abordar as áreas que precisam de remediação descobertas através da avaliação do ambiente. Você precisa incluir a avaliação de prontidão de serviço e o plano de remediação como parte do plano de sucesso.

### <a name="adoption-plan"></a>Plano de adoção

Após a avaliação de prontidão para adoção, deve ser feito um planejamento detalhado adicional para que a equipe do projeto estabeleça um conjunto abrangente de planos de comunicação, plano de treinamento e atividades de adoção pré-lançamento, no lançamento e pós-lançamento.

Os recursos para dar suporte às atividades de adoção, como folhetos, e-mails de boas-vindas e materiais de treinamento, são identificados nesta etapa, juntamente com as personalizações necessárias para atender aos requisitos organizacionais.

Os modelos para as atividades de adoção estão disponíveis [aqui](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plano operacional

O exercício de mapeamento de funções operacionais estabelecerá as funções, as responsabilidades e as equipes atribuídas a cada função operacional para dar suporte à implementação do Sistema de Telefonia com Planos de Chamadas.

Você precisa inserir isso e incluir o plano operacional como parte do plano de sucesso para garantir a prontidão operacional da solução.

<br>
Planejamento técnico do Sistema de Telefonia com Planos de Chamadas
------------------------------------------------------

Para planejar a implementação técnica do Sistema de Telefonia com Planos de Chamadas, é necessário tomar uma série de decisões antecipadamente para melhor preparar a sua organização para implementar uma solução que atenda aos requisitos da empresa. Essas decisões serão documentadas no plano de implementação técnica.

## <a name="availability-of-calling-plans"></a>Disponibilidade de Planos de Chamadas

Para descobrir onde o serviço de Planos de Chamadas está disponível, consulte [Disponibilidade de Audioconferência e Planos de Chamadas por países e regiões](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais, para que os Planos de Chamadas estejam disponíveis para organizações multinacionais, o contrato de assinaturas do Office 365 deve ser obtido de países e regiões cobertos pelo serviço de Planos de Chamadas ou de onde o serviço de Planos de Chamadas está disponível comercialmente.

Depois de confirmar a qualificação de sua organização para obter o complemento de Planos de Chamadas, compile a lista dos locais de usuários ou escritórios onde o serviço de Planos de Chamadas será implementado com base na lista de países e regiões disponíveis.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida os locais de usuários ou escritórios nos quais o serviço de Planos de Chamadas será implementado</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os locais de usuários ou escritórios que implementarão o serviço de Planos de Chamadas</li></ul>|

> [!TIP]
> Segue um exemplo de lista de habilitação de locais do Sistema de Telefonia com Planos de Chamadas:
>|Escritório   |Localização |Serviço de Sistema de Telefonia  |
>|---------|---------|---------|
>|One Epping Road|Austrália|Serviço PSTN herdado|
>|100 Alma Road|Hong Kong SAR|Serviço PSTN herdado|
>|One Marina Boulevard|Cingapura|Serviço PSTN herdado|
>|32 London Bridge Street|Reino Unido|Sistema de Telefonia com Planos de Chamadas|
>|39 quai du Président Roosevelt|França|Sistema de Telefonia com Planos de Chamadas|

## <a name="licensing-for-calling-plans"></a>Licenciamento de Planos de Chamadas

Os Planos de Chamadas são um complemento ao recurso Sistema de Telefonia do Office 365, então você precisa ter uma licença do Sistema de Telefonia habilitada para usar os Planos de Chamadas.

A [licença do Sistema de Telefonia](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) está disponível como parte dos planos de assinatura do Office 365 E5 ou como um complemento aos planos de assinatura do Office 365 E1 ou Office 365 E3.
Há dois tipos de [licenças do Plano de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365):

-   Plano de Chamadas Domésticas
-   Plano de Chamadas Internacionais e Domésticas

> [!NOTE]
> O local de uso do Office 365 atribuído ao usuário determina o que é considerado “doméstico” para um usuário específico.

Cada tipo de Plano de Chamadas fornece uma alocação de minutos de chamadas que os usuários podem usar por mês para fazer chamadas domésticas ou internacionais. O Plano de Chamadas Domésticas custa menos que o Plano de Chamadas Internacionais e Domésticas. Para saber quantos minutos estão disponíveis para cada país/região, consulte a seção "Planos de Chamadas" de [Disponibilidade de Audioconferência e Planos de Chamadas por países e regiões](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

Normalmente, nem todas as pessoas de uma organização precisam fazer chamadas internacionais. A flexibilidade de assinar e atribuir o tipo de Plano de Chamadas mais apropriado para os requisitos de negócios de cada usuário permite que a organização controle os custos de implementação dos Planos de Chamadas.

Para cada locatário do Office 365, o número combinado de minutos de chamadas é agrupado por país ou região e por tipo de Plano de Chamadas. Quando o limite mensal de minutos de chamadas do locatário é alcançado, o serviço de Planos de Chamadas (exceto as chamadas de emergência) é suspenso até o final do mês. Os serviços de Planos de Chamadas serão retomados automaticamente no primeiro dia do mês calendário seguinte.

Para que os usuários possam fazer chamadas de saída depois que os minutos de chamadas terminarem sem precisar esperar até o ciclo de cobrança do mês seguinte, você pode configurar Créditos de Comunicação para a sua organização. Os [Créditos de Comunicação](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) também possibilitam que os usuários que têm um Plano de Chamadas Domésticas atribuído façam chamadas internacionais cobradas com base em um modelo de “pagamento por minuto”.

A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados. Os valores de fundos recomendados podem ser consultados no artigo [Créditos de Comunicação](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

Se a sua organização optar por usar a recarga automática, uma recomendação sobre o gatilho (menor valor de fundos) também está incluída no artigo [Créditos de Comunicação](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits). O valor da recarga automática deve ser determinado pelo uso real. O uso de Créditos de Comunicação deve ser monitorado ao longo do tempo e o valor da recarga precisa ser ajustado conforme a necessidade.

É possível controlar o uso de Créditos de Comunicação por usuário. Assim, você pode garantir que a funcionalidade seja atribuída a pessoas da organização que têm necessidades de negócios correspondentes.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se a sua organização não tem a licença necessária do Sistema de Telefonia, decida se ela será adquirida com a elevação das assinaturas existentes do Office 365 ou com a aquisição de complementos do Sistema de Telefonia</li><li>Decida quais usuários precisam da licença do Plano de Chamadas Domésticas e quais precisam da licença do Plano de Chamadas Domésticas e Internacionais</li><li>Decida se os Créditos de Comunicação são necessários para a implementação dos Planos de Chamadas. Em caso positivo, decida o valor inicial de fundos a serem comprados. Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</li><li>Decida quais usuários precisam usar a licença de Créditos de Comunicação</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente a quais usuários a licença do Sistema de Telefonia deve ser atribuída junto com a licença do Plano de Chamadas Domésticas, e a quais usuários a licença do Sistema de Telefonia deve ser atribuído junto com a licença do Plano de Chamadas Domésticas e Internacionais</li><li>Documente o plano de Créditos de Comunicação (valor inicial, valor do gatilho, valor da recarga automática)</li><li>Documente os usuários que devem ter a licença de Créditos de Comunicação habilitada</li></ul>|

> [!TIP]
> Você pode documentar a lista de atribuição de licenças para usuários do Sistema de Telefonia com Planos de Chamadas usando este exemplo:
>|Usuário  |Escritório  |Licença do Office 365  |Créditos de Comunicação  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Office 365 E5, Plano de Chamadas Internacionais e Domésticas|Habilitado|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5, Plano de Chamadas Domésticas|Desabilitado|
>|Pradeep Gupta|32 London Bridge Street|Office 365 E5, Plano de Chamadas Domésticas|Habilitado|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento do Sistema de Telefonia, Plano de Chamadas Domésticas|Desabilitado|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5, Plano de Chamadas Internacionais e Domésticas|Habilitado|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento do Sistema de Telefonia, Plano de Chamadas Domésticas|Desabilitado|

<br>
> [!TIP]
> Os números do planejamento de seus Créditos de Comunicação podem ser documentados da seguinte maneira:
>|         |         |
>|---------|---------|
>|Valor inicial|US$ 1.000|
>|Valor do gatilho|US$ 400|
>|Valor da recarga automática|TBA|

## <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com os Planos de Chamadas do Office 365, cada usuário de sua organização precisa ter um número de telefone DID (discagem direta interna) exclusivo e um [endereço de emergência validado](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing) correspondente.

Os números de telefone podem ser [obtidos diretamente da Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization), e números de telefone existentes podem ser [transferidos (portados) para a Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).

> [!NOTE]
> A complexidade da transferência de números de telefone para a Microsoft varia muito com base nos países ou regiões, operadoras, o número de circuitos envolvidos e vários outros fatores. Para planejar a portabilidade dos números de telefone, consulte os detalhes no [Guia de Portabilidade de Números](https://go.microsoft.com/fwlink/?linkid=859011).

Para obter números de telefone diretamente da Microsoft, use uma destas opções:

- [Centro de administração do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)
- [Cmdlets do Windows PowerShell remoto](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
- [Enviar um formulário de nova solicitação de número de telefone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

O formulário de solicitação de novo número de telefone funciona melhor para a aquisição planejada de um número de telefone, pois você pode solicitar um bloco de números de telefone contíguos. A obtenção de números de telefone usando o Centro de administração do Skype for Business ou o Windows PowerShell remoto não está disponível em todos os países ou regiões.

Os dois primeiros métodos, usando o Centro de administração do Skype for Business ou o Windows PowerShell remoto, funcionarão para a aquisição imediata e única de um número de telefone, e quando não é necessário um bloco de números de telefone contíguos.

> [!NOTE]
> Há um limite da [quantidade de números de telefone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get) que podem ser adquiridos da Microsoft de acordo com o número de licenças do Plano de Chamadas assinadas por sua organização. Para números de telefone de usuário (assinante), a fórmula para fazer esse cálculo é (número de licenças do Plano de Chamadas Domésticas + Plano de Chamadas Domésticas e Internacionais) x 1,1 +10. Por exemplo, se você tem 50 usuários com licenças do Plano de Chamadas, pode adquirir 65 números de telefone ((50 x 1,1) + 10).

Ao configurar os números de telefone para os Planos de Chamadas, é necessário atribuir um endereço de emergência para cada número de telefone antes de atribuí-lo a um usuário. Isso é necessário para dar suporte às chamadas de emergência. O endereço de emergência deve ser validado para garantir que esteja no formato correto para ser usado pelos serviços de resposta a emergências.

> [!IMPORTANT]
> No serviço de Planos de Chamadas, as chamadas para serviços de emergência funcionam de modo diferente dos serviços telefônicos tradicionais. É importante que você entenda essas diferenças e as comunique para todos os usuários. Confira mais detalhes em [Termos e condições para chamadas de emergência](https://docs.microsoft.com/SkypeForBusiness/legal-and-regulatory/emergency-calling-terms-and-conditions).

Além do endereço de emergência validado, os locais de emergência podem ser definidos e associados a endereços de emergência validados para fornecer uma localização mais exata de um endereço. Normalmente, um local de emergência consiste no número de um edifício, andar, bloco ou o número do escritório onde o usuário está localizado.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida como os números de telefone serão obtidos para locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas (obter da Microsoft ou transferir números de telefone existentes)</li><li>Se você optar por adquiri-los da Microsoft, decida o método para obter os números de telefone (envio de formulários ou automatizado) para os locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas</li><li>Decida o nível de granularidade das informações de locais de emergência de devem ser coletadas para os locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente o plano mestre para a aquisição de números de telefone, detalhando como os números de telefone serão obtidos para cada um dos locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas</li><li>Se aplicável, preencha <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">o formulário de solicitação de novo número de telefone</a>, um formulário para cada local ou escritório</li><li>Se você optar por transferir números de telefone existentes, confira o <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guia de Portabilidade de Números</a> para planejar a ajustar corretamente o cronograma de implementação dos Planos de Chamadas</li><li>Documente detalhadamente o endereço de emergência e os locais de emergência para cada um dos locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas</li></ul>

> [!TIP]
> Os detalhes da aquisição de números de telefone, os números de telefone e os detalhes dos locais de emergência podem ser documentados usando este modelo:
>|Usuário  |Local e endereço de emergência  |Aquisição de números de telefone  |Número de telefone  |
>|---------|---------|---------|---------|
>|Emily Braun|1034/32 London Bridge Street, Londres, SE1, Reino Unido|Porta existente|+44 20 7946 0034|
>|Lidia Holloway|1023/32 London Bridge Street, Londres, SE1, Reino Unido|Porta existente|+44 20 7946 0065|
>|Pradeep Gupta|1023/32 London Bridge Street, Londres, SE1, Reino Unido|Porta existente|+44 20 7946 0023|
>|Marcel Beauchamp|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, França|Adquirir novo|TBA|
>|Rachelle Cormier|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, França|Adquirir novo|TBA|
>|Isabell Potvin|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, França|Adquirir novo|TBA|

## <a name="voicemail"></a>Caixa postal

A caixa postal do Sistema de Telefonia, alimentada pelos serviços de caixa postal do Azure, dá suporte a depósitos de caixa postal somente na caixa de correio do Exchange e não é compatível com sistemas de email de terceiros.

Por padrão, a caixa postal do Sistema de Telefonia funciona com o Exchange Online, mas exige [um modelo de implantação e uma versão do Exchange local com suporte](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) para permitir a entrega de mensagens da caixa postal nas caixas de correio do usuário na implantação do Exchange local.

A caixa postal do Sistema de Telefonia apresenta transcrição da caixa postal e, por padrão, está habilitada para todos os usuários da organização. Em alguns casos, sua empresa pode ter requisitos para desabilitar a transcrição da caixa postal para determinados usuários ou em toda a organização.

> [!NOTE]
> Foi implementado um mecanismo de fallback de modo que a caixa postal do Sistema de Telefonia possa reenviar mensagens usando o protocolo SMTP. Isso quer dizer que os usuários com uma caixa de correio em um sistema de email de terceiros receberá suas mensagens da caixa postal. Não há garantia de tempo de atividade do serviço ou de outros recursos de caixa postal, como a alteração da saudação e outras configurações da caixa postal.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a caixa postal do Sistema de Telefonia será habilitada para a implementação de Planos de Chamadas</li><li>Se o uso do Exchange local e da implantação existente não atender aos requisitos para dar suporte à caixa postal do Sistema de Telefonia, decida sobre as opções disponíveis (atualização e instalação para dar suporte à caixa postal do Sistema de Telefonia ou migração para o Exchange Online, utilização do mecanismo de fallback)</li><li>Decida se a transcrição da caixa postal deve ser habilitada/desabilitada em toda a organização ou para usuários específicos</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Se aplicável, documente os pontos de decisão do Exchange para dar suporte à caixa postal do Sistema de Telefonia</li><li>Se a caixa postal e a transcrição da caixa postal não forem habilitadas para todos os usuários, documente quais usuários deverão ter esses recursos habilitados</li></ul>|

> [!TIP]
> Os detalhes da caixa postal do Sistema de Telefonia para a implementação do Sistema de Telefonia com Planos de Chamadas podem ser documentados da seguinte maneira:
>|Usuário  |Caixa de correio do Exchange  |Habilitar caixa postal  |Transcrição da caixa postal  |
>|---------|---------|---------|---------|
>|Emily Braun|Online|Sim|Habilitado|
>|Lidia Holloway|Online|Sim|Habilitado|
>|Pradeep Gupta|No local|Sim|Habilitado|
>|Marcel Beauchamp|No local|Sim|Desabilitado|
>|Rachelle Cormier|Online|Sim|Desabilitado|
>|Isabell Potvin|No local|Sim|Desabilitado|

## <a name="calling-identity"></a>Identificação de chamadas

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identificação de chamadas (ID de Chamadas). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Em alguns casos, há requisitos de negócios legítimos para mascarar a ID de Chamadas a fim de proteger a identidade do autor da chamada usando o número da linha principal do escritório. Normalmente, é um número de serviço atendido com a configuração do [Atendedor Automático](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants), como a ID de Chamadas ou para bloquear totalmente a apresentação da ID de Chamadas.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a manipulação da ID de Chamadas é necessária para a implementação dos Planos de Chamadas.</li><li>Se aplicável, decida os tipos de manipulação da ID de Chamadas (mascarar com o número de serviço ou manter o anonimato) que devem ser implementados</li><li>Se aplicável, decida qual usuário requer a manipulação da ID de Chamadas e o tipo de manipulação da ID de Chamadas que deve ser atribuído a cada usuário</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os usuários que devem ter a manipulação de ID de Chamadas atribuída e o tipo de manipulação de ID de Chamadas aplicável a cada usuário</li></ul>|

> [!TIP]
> Segue um exemplo de documentação de detalhes do mascaramento de ID de Chamadas:
>|Usuário  |Habilitar mascaramento de ID de Chamadas de saída  |Tipo de mascaramento de ID de Chamadas  |Permitir a substituição pelo usuário  | Habilitar mascaramento de ID de Chamadas de entrada  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|Não|N/D|Sim|Não|
>|Lidia Holloway|Sim|Número de serviço (OrgAA, +44 20 7946 0000)|Não|Sim|
>|Pradeep Gupta|Não|N/D|Sim|Não|
>|Marcel Beauchamp|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|
>|Rachelle Cormier|Sim|Manter o anonimato|Sim|Não|
>|Isabell Potvin|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|

## <a name="dial-plans"></a>Planos de discagem

O [Plano de Discagem](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) do recurso do Sistema de Telefonia do Office 365 é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente o formato[E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para autorização e roteamento de chamadas. 

Um plano de discagem permite que os usuários disquem números de telefone da forma como estão acostumados, por exemplo, omitindo o código de área para chamadas locais, omitindo o código de país para chamadas domésticas ou até usando atalhos de discagem ao fazer uma chamada telefônica.

Dentro do recurso Sistema de Telefonia do Office 365, existem dois tipos de planos de discagem:

-   **Plano de discagem para serviço**. Esse é o plano de discagem padrão, é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.
-   **Plano de discagem para locatários**. Esse é um plano de discagem personalizável em um locatário e é dividido em mais dois tipos:
    -   **Plano de discagem para locatário global** – o plano de discagem se aplica para todos os usuários do locatário.
    -   **Plano de discagem para locatário usuário** – o plano de discagem se aplica apenas a usuários específicos.

> [!NOTE]
> Confira mais detalhes e exemplos em [O que são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

O plano de discagem efetivo atribuído aos usuários é a combinação do plano de discagem para serviço (com base no local de uso do Office 365 do usuário) e do plano de discagem para locatários (que pode ser o plano de discagem para locatário global ou o plano de discagem para locatário usuário).

![A tabela mostra três combinações de planos de discagem para locatários e serviços.](media/audio_conferencing_image8.png)

Há um máximo de 25 regras de normalização em cada plano de discagem para locatários e, portanto, a duplicação das regras de normalização já disponíveis como parte do plano de discagem para serviço precisa ser evitada.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a sua organização requer planos de discagem personalizados (requisitos de negócios, requisitos de adoção etc.).</li><li>Se aplicável, decida o escopo do plano de discagem de locatário (locatário global ou locatário usuário) para dar suporte aos requisitos dos planos de discagem personalizados</li><li>Se aplicável, decida os planos de discagem de locatário que serão criados para oferecer suporte a locais de usuários ou escritórios que estão no escopo de implementação dos Planos de Chamadas</li><li>Se aplicável, decida qual usuário requer um plano de discagem personalizado e o plano de discagem de locatário que deve ser atribuído a cada usuário</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os planos de discagem personalizados e as regras de normalização associadas que devem ser configuradas como parte da implementação dos Planos de Chamadas</li><li>Documente os usuários aos quais deve ser atribuído um plano de discagem personalizado e o plano de discagem de locatário a ser atribuído a cada usuário</li></ul>|

> [!TIP]
> Se aplicável para o seu projeto, você pode usar o modelo a seguir para documentar das configurações dos planos de discagem de locatário:
>|Nome do plano de discagem de locatário<br>_Descrição  |Nome das regras de normalização<br>_Descrição_  |Padrão<br>Conversão<br>IsInternalExtension  |
>|---------|---------|---------|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan_|**FR-39qdPR-Internal**<br>_Número interno (x7000 – x7999) para o escritório de 39 quai du Président Roosevelt, Issy-les-Moulineaux, França_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalização de número gratuito na França_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalização de número de serviço na França_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>
> [!TIP]
> O modelo de exemplo a seguir pode ser utilizado para documentar atribuições de planos de discagem para dar suporte ao seu projeto:
>|Usuário  |Escritório  |Tipo do plano de discagem  |Nome do plano de discagem  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Plano de discagem para serviço|N/A|
>|Lidia Holloway|32 London Bridge Street|Plano de discagem para serviço|N/A|
>|Pradeep Gupta|32 London Bridge Street|Plano de discagem para serviço|N/A|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-39qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-39qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-39qdPR|

## <a name="document-technical-implementation-plan"></a>Documentar o plano de implementação técnica

Utilizar os pontos de decisão acima para documentar o seu plano de implementação técnica.
Esse plano de implementação técnica fornecerá à equipe do projeto, que pode incluir um parceiro de implantação ou FastTrack, as informações necessárias para executar a integração técnica para a implementação do Sistema de Telefonia com Planos de Chamadas.

No geral, um plano de implementação técnica deve conter as seguintes seções principais:

-   Lista de habilitação de locais do Sistema de Telefonia com Planos de Chamadas

-   Atribuição de licenças a usuários do Sistema de Telefonia com Planos de Chamadas

-   Número de planejamento de Créditos de Comunicação

-   Detalhes sobre a aquisição de números de telefone, números de telefone e locais de emergência

-   Detalhes de configuração da caixa postal

-   Detalhes de configuração do mascaramento de ID de Chamadas

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

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

[Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/configuring-teams-calling-quickstartguide)
