---
title: Definir sucesso em Conferências de Áudio, Sistema de Telefonia com Planos de Chamadas ou Sistema Telefônico de Roteamento Direto - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Meça os resultados da sua conferência de áudio, sistema telefônico com planos de chamadas ou implantação de roteamento direto do sistema telefônico e verifique se você obteve os resultados desejados.
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: a84f0d38afbac74b296ccdfed626d6f8830d46a9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244160"
---
# <a name="define-my-success"></a>Definir meu sucesso

Este artigo fornece uma visão geral dos requisitos para a definição do sucesso da implantação de audioconferência, sistema telefônico com planos de chamada ou roteamento direto do sistema telefônico para sua organização. Ao definir apropriadamente qual será a aparência do sucesso, você pode medir seus resultados enquanto avança pela implantação e verifica se os resultados que você obtém são os que você deseja.

<!--ENDOFSECTION-->

A **videoconferência** fornece às organizações mais pontos de entrada adicionais para qualquer reunião (ad hoc ou agendada), permitindo que os participantes da reunião ingressem via PSTN (rede telefônica pública comutada) por meio da discagem usando telefones fixos e celulares convencionais Agência telefônica (PBX) ou telefones celulares. Isso é útil quando o organizador ou os participantes não estão na frente de um computador ou quando as conexões de dados estão indisponíveis ou não são muito confiáveis para dar suporte à comunicação por voz, como em uma área remota com cobertura de dados móvel, ou conectadas a uma rede Wi-Fi pública e gratuita serviço com largura de banda limitada ou quando os participantes da reunião preferem discar para a reunião usando um ponto de extremidade de telefonia acessível para eles.

O **sistema telefônico com planos de chamada ("planos de chamada")** oferece às organizações uma maneira de modernizar seu local de trabalho, permitindo que os usuários façam chamadas telefônicas relacionadas a negócios em seus computadores e dispositivos móveis. A modernização do local de trabalho pode fazer parte de qualquer número de cenários, uma implementação de trabalho baseada em atividades, uma grande mudança do Office, uma atualização para o Office em destaque, a desativação de uma solução PBX herdada, a conclusão de um contrato de provedor de serviço PSTN e assim por diante. Com os planos de chamada, a Microsoft facilita a conectividade com a PSTN.

O **Roteamento direto do sistema de telefonia ("roteamento direto")** fornece às organizações os mesmos benefícios listados acima para planos de chamada, exceto que a conectividade PSTN é facilitada por um provedor de terceiros, em vez da Microsoft. Isso permite a implantação em países em que os planos de chamada não estão disponíveis ou em implantações em que um contrato de provedor de serviços PSTN existente precisa ser mantido ou a interoperabilidade com certos sistemas locais é necessária. Um cenário adicional a considerar o roteamento direto é a interoperabilidade do sistema de telefonia. Durante a transição dos usuários para chamadas no Teams, alguns usuários podem permanecer em PBXs herdadas. O roteamento direto permite que os casos de uso coexistam. O tráfego de chamadas entre os usuários em sistemas herdados e usuários do teams permanecem dentro da organização.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso empresarial para videoconferências, planos de chamadas ou roteamento direto

Para começar, os principais participantes do projeto precisam definir casos de uso empresarial que dão suporte à implementação de videoconferência, planos de chamada ou roteamento direto.

Os casos de uso para empresas devem definir e documentar resultados de negócios desejados e desejados e incluir os seguintes itens:

-   Descrição do processo empresarial atual

-   Desafios do processo empresarial existente

-   Como a tecnologia pode ajudar a superar esses desafios

-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para videoconferência:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.|
> |**Desafios com os processos comerciais existentes**<br>A contoso ocupa cerca de USD1 milhões por ano para o serviço de conferência PSTN atual, com 75% do custo incorrido para reuniões internas. O uso de pontos de extremidade de telefonia tradicionais para ingressar nas reuniões hospedadas pelo serviço de conferência PSTN não está alinhado ao plano da organização para adotar o Teams como uma plataforma moderna de comunicação e colaboração.|
> |**Como a tecnologia pode superar esses desafios**<br>Com a adoção do Microsoft Teams como uma plataforma moderna de comunicação e colaboração, os usuários internos devem ingressar principalmente em reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião. O serviço de audioconferência estará disponível para dar suporte a participantes externos ou para situações de suporte em que o uso do áudio do computador não seja favorável para os participantes internos.|
> |**Resultados comerciais esperados e mensuráveis**<br>A mudança para o Microsoft Teams, como uma plataforma de comunicação e colaboração moderna, combinada com o serviço de audioconferência, reduzirá consideravelmente o custo para fornecer o serviço de conferência PSTN.|

<br>

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para planos de chamada:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do Office da Contoso inclui um telefone de mesa para cada mesa. Cada funcionário recebeu um número de telefone do Direct Inward Dialing (DID). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados à PSTN por meio de um tronco SIP (Session Initiation Protocol). Os funcionários só podem fazer e receber chamadas telefônicas nos telefones da área de trabalho atribuído.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones da área de trabalho mostra que somente 10% dos telefones da área de trabalho são usados ativamente, com o REST configurado para encaminhar chamadas para telefones celulares ou para tocar simultaneamente em telefones celulares. Manter o sistema PBX existente e telefones associados da área de trabalho contribui para 20% do custo mensal de serviço de telefonia da contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>Os planos de chamada permitirão que o computador pessoal de um usuário receba e faça chamadas telefônicas pela rede de dados aproveitando o aplicativo nativo do Microsoft Teams. Isso remove a necessidade de implementar e manter telefones da área de trabalho e abre a oportunidade de descomissionar o sistema PBX existente, porque o serviço de telefonia pode ser entregue por meio da nuvem pela rede sem nenhuma dependência de um sistema de telefonia tradicional.|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e a descomissionamento do PBX herdado e dos telefones de mesa oferecerá uma redução de 20% nas despesas de serviços de telefonia mensais. Os planos de chamada simplificarão os espaços de trabalho do Office, permitindo que a contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia.|

<br>

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para roteamento direto:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do Office da Contoso inclui um telefone de mesa para cada mesa. Cada funcionário recebeu um número de telefone do Direct Inward Dialing (DID). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados à PSTN por meio de um tronco SIP (Session Initiation Protocol). Os funcionários só podem fazer e receber chamadas telefônicas nos telefones da área de trabalho atribuído.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones da área de trabalho mostra que somente 10% dos telefones da área de trabalho são usados ativamente, com o REST configurado para encaminhar chamadas para telefones celulares ou para tocar simultaneamente em telefones celulares. Manter o sistema PBX existente e telefones associados da área de trabalho contribui para 20% do custo mensal de serviço de telefonia da contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>O contrato do provedor de tronco SIP foi assinado recentemente e estará em vigor por três anos. O roteamento direto permite que a conectividade PSTN seja fornecida pelo provedor de tronco SIP e também permite que o computador pessoal de um usuário receba e faça chamadas telefônicas pela rede de dados aproveitando o aplicativo nativo do Microsoft Teams. Isso remove a necessidade de implementar e manter telefones da área de trabalho e abre a oportunidade de descomissionar o sistema PBX existente, mantendo uma superfície de SBC (Session Border Controller) limitada.|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e a descomissionamento do PBX herdado e dos telefones de mesa oferecerá uma redução de 20% nas despesas de serviços de telefonia mensais. O roteamento direto simplificará os espaços de trabalho do Office, permitindo que a contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia.|

Além de definir seus casos de uso empresarial, para definir os limites do projeto, você deve se orientar para impulsionar a clareza de acordo com:

-   **Escopo organizacional:** A implementação de videoconferência, planos de chamada ou roteamento direto pode abranger toda a organização ou apenas unidades de negócios específicas.

-   **Cronograma do projeto:** A linha do tempo específica que o projeto vai executar.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Pontos de decisão|<ul><li>Quais são os casos de uso empresarial da videoconferência que você pode identificar em sua organização?</li><li>Quais são os casos de uso empresarial para planos de chamadas que você pode identificar em sua organização?</li><li>Quais são os casos de uso empresarial do roteamento direto que você pode identificar em sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os casos de uso de negócios da conferência de áudio para sua organização.</li><li>Documente todos os casos de uso de negócios para planos de chamadas para sua organização.</li><li>Documentar todos os casos de uso de negócios para roteamento direto para sua organização.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas

Os casos de uso empresarial definidos na etapa anterior incluem um escopo organizacional para a videoconferência, planos de chamada ou implementação de roteamento direto. Com base nele, você pode preencher a matriz de participantes abrangentes para incluir as pessoas certas para envolver o projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
> 
> |Função  |Descrição  |Nome, informações de contato, localização  |
> |---------|---------|---------|
> |Patrocinador executivo do projeto|<ul><li>Tire o máximo de autoridade e responsabilidade do projeto e da entrega nos objetivos do projeto.</li><li>Ajudar a solucionar problemas escalonados pelo cliente potencial do projeto.</li><li>A comunicação do patrocinador dentro da empresa sobre os objetivos do projeto.</li><li>Faça decisões estratégicas importantes.</li><li>Garanta a disponibilidade de recursos obrigatórios e orçamento.</li><li>Análises trimestrais dos negócios (QBRs).</li><li>Compre e dê suporte aos esforços da campanha de conscientização.</li><li>Servir como patrocinador do projeto para a distribuição do programa.</li></ul>|TBA|
> |Líder de projeto|<ul><li>Gerenciar e conduzir a equipe do projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidos no projeto.</li><li>Seja possível para criar e gerenciar planos de projeto para atender a resultados trimestrais de chave.</li><li>Solucionar problemas de funcionalidade interfuncional.</li><li>Forneça atualizações regulares para os patrocinadores do projeto.</li><li>Incorpore aspectos de adoção no plano de projeto tudo.</li><li>Liderar análises mensais de negócios e operacionais (MBRs), contribuir para o QBRs.</li></ul>|TBA|
> |Líder/arquiteto de colaboração|<ul><li>Executar na estratégia de colaboração definida pelos executivos da empresa.</li><li>Analise e escolha produtos de colaboração que atendam às metas de negócios da empresa.</li><li>Operações de design para produtos de colaboração.</li><li>Definir modelos de operação e suporte.</li><li>Contribuir com análises mensais e trimestrais para empresas.</li></ul>|TBA|
> |Consultor|<ul><li>Ser responsável pelos serviços de configuração</li><li>Contribuir para a arquitetura geral da solução.</li></ul>|TBA|
> |Gerente de projetos|<ul><li>Desenvolva e mantenha o plano do projeto.</li><li>Gerencie resultados finais do projeto em linha com o plano e o orçamento do projeto.</li><li>Registre e gerencie problemas de projeto, incluindo escalonamentos.</li><li>Realize chamadas standup semanais.</li><li>Liaise com e forneça atualizações para os patrocinadores executivos do projeto.</li><li>Trabalhe com o arquiteto para definir a abordagem de gerenciamento de alterações e os planos de comunicação.</li></ul>|TBA|
> |Especialista em adoção/gerenciamento de mudanças|<ul><li>Fornecer entrada durante a fase de descoberta para processos de adoção e treinamento.</li><li>Participe do workshop de estratégia de adoção.</li><li>Desenvolva e assuma a responsabilidade pela estratégia de adoção.</li><li>Desenvolva e execute o plano de comunicação.</li><li>Entregar treinamentos aos usuários.</li><li>Coletar comentários e conduzir pesquisas.</li></ul>|TBA|
> |Líder de rede|<ul><li>Fornecer entrada durante a fase de descoberta no design de rede.</li><li>Participe do planejamento durante o workshop de fase do enVision.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>|TBA|
> |Líder de segurança|<ul><li>Fornecer entrada durante a fase de descoberta no design e nos processos de segurança.</li><li>Participe do planejamento durante o workshop de fase do enVision.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>|TBA|
> |Líder de telefonia|<ul><li>Forneça a entrada durante a fase de descoberta no design de telefonia.</li><li>Participe do planejamento durante o workshop de fase do enVision.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>|TBA|
> |Líder de desktop|<ul><li>Forneça a entrada durante a fase de descoberta para os clientes e o processo de atualização.</li><li>Participe do planejamento durante o workshop do enVision.</li><li>Coordene o trabalho da equipe da área de trabalho durante a execução do projeto.</li></ul>|TBA|
> |Líder de suporte/suporte técnico|<ul><li>Fornecer entrada durante a fase de descoberta em modelos operacionais e de suporte.</li><li>Participe do planejamento durante o workshop de fase do enVision.</li><li>Participe do planejamento do modelo de suporte.</li><li>Coordene o trabalho de equipes e recursos de suporte durante a execução do projeto.</li></ul>|TBA|
> |Representantes das unidades de negócios|<ul><li>Contribuir com guias e materiais de adoção baseados em usuário.</li><li>Contribuir para e revisar os casos de uso de negócios.</li></ul>|TBA|
> |Líder de implantação|<ul><li>Certifique-se de que os pré-requisitos de implantação sejam atendidos.</li><li>Envolver recursos a serem envolvidos nas atividades de fase onboard.</li><li>Participar de reuniões para revisar e preparar relatórios sobre o status de implantação.</li></ul>|TBA|
> |Administradores de TI|<ul><li>Assistência com o planejamento e a execução de testes. Esta função é para profissionais de ti.</li></ul>|TBA|
> |Proprietário do serviço|<ul><li>Seja responsável pela operação da conferência de áudio, dos planos de chamada ou do serviço de roteamento direto, tudo.</li><li>É o proprietário da videoconferência, dos planos de chamada ou do serviço de roteamento direto.</li></ul>|TBA|
> |Defensores da qualidade|<ul><li>Qualidade da unidade, confiabilidade e comentários dos usuários.</li><li>Identifique tendências de qualidade e remediação de drives com as respectivas equipes.</li><li>Faça o relatório de volta ao Comitê de direcionamento para a liderança.</li><li>Informe a qualidade, a confiabilidade e o relatório do usuário por meio da tarifa de minha chamada e da Pontuação do Promonte líquido.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Quem preencherá cada função importante do interessado em sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os principais participantes e comunique as responsabilidades e as expectativas da função para cada indivíduo atribuído.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir OKRs, KSIs e riscos

Com os participantes do projeto montados, você pode traduzir casos de uso empresarial, escopo organizacional e linhas do tempo do projeto em objetivos e resultados de chave (OKRs), e as medidas do sucesso do projeto podem ser definidas como uma lista de indicadores de sucesso de chave (KSIs).

A participação completa de participantes do projeto na definição de OKRs e KSIs é essencial para ajudar a garantir uma noção de propriedade e alinhar essas medidas de sucesso às necessidades comerciais organizacionais.

OKRs contém os objetivos que você definiu no início do projeto e define resultados de chave mensuráveis trimestralmente. Revise os resultados da chave mensalmente para acompanhar o status do projeto geral e, com base em andamento, você ajusta planos trimestrais conforme o necessário.

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de audioconferência podem ser referenciados abaixo:
> <br>
> 
> **Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
> 
> |Objetivos  |Resultados da chave  |Para fazer  |
> |---------|---------|---------|
> |Implantar Audioconferência no Teams até o final do ano fiscal de 2018|1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018|2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de planos de chamada podem ser referenciados abaixo:
> <br>
> 
> **Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
> 
> |Objetivos  |Resultados da chave  |Para fazer  |
> |---------|---------|---------|
> |Implantar planos de chamadas nas filiais européias pelo final do ano fiscal 2018|FY18Q3: implantar planos de chamada em Londres Office|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Descomissionar o PBX herdado em Londres Office pelo final do ano fiscal 2018|FY18Q4: descomissionar PBX herdada em Londres Office|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|
> 
> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de roteamento direto podem ser referenciados abaixo:
> <br>
> 
> **Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
> 
> |Objetivos  |Resultados da chave  |Para fazer  |
> |---------|---------|---------|
> |Implantar o roteamento direto nas filiais canadenses pelo final do ano fiscal 2018|FY18Q3: implantar o roteamento direto em Toronto Office|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Descomissionar o PBX herdada do escritório Toronto pelo fim do ano fiscal 2018|FY18Q4: descomissionar PBX herdada em Toronto Office|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

KSIs medem a qualidade e o sucesso dos resultados da chave e complementam a natureza binária de OKRs (alcançada ou não alcançada), detalhando os resultados bons e/ou inválidos.

Ao definir KSIs, recomendamos que você use critérios "específicos, mensuráveis, mensurável, atribuíveis, realísticos e relacionados a tempo" (inteligentes):

-   Específico: direcionar uma área específica para melhorias

-   Mensurável: quantificar ou pelo menos sugerir um indicador de progresso

-   Atribuível: Especifique quem fará isso

-   Realística: declare quais resultados podem ser alcançados de forma realista, dadas os recursos disponíveis

-   Relacionados ao tempo: especifique quando os resultados podem ser obtidos

> [!TIP]
> Este é um exemplo de KSI relevante para esse projeto:
> 
> |Tipo  |Pergunta e critérios do KSI  |Como foi mensurado  |Critérios de sucesso  |Mensurado  |Responsável  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adoção|A qualidade da chamada é igual ou melhor que a solução anterior|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Esquipe de Tecnologia da Informação|
> |Uso/adoção|O Microsoft Teams facilitou o processo de comunicação|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/adoção|Os usuários usam a solução ativamente|Relatórios do Office 365, Painel de Qualidade da Chamada|80% dos usuários são usuários ativos diariamente|Diário|Equipe de gerenciamento de mudanças|
> |Uso/qualidade|A porcentagem de chamadas/conferências de má qualidade deve ser mínima|Painel de Qualidade da Chamada|< 5% de chamadas de má qualidade por mês|Diariamente|Esquipe de Tecnologia da Informação|
> |Uso/suporte|Eu sei como obter suporte técnico|Pesquisa|90% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/suporte|Estou satisfeito com a qualidade do suporte técnico|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após cada incidente|Esquipe de Tecnologia da Informação|
> |Financeiro|Redução dos minutos de conferência herdados|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Você precisa identificar riscos empresariais como parte deste exercício e definir um plano de mitigação para cada risco identificado. Essas informações podem ser capturadas em um registro de riscos.

> [!TIP]
> Seu registro de risco pode ser documentado como exemplo abaixo:
> 
> |Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
> |---------|---------|---------|---------|---------|
> |A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas mescladas, crie uma OKR separada que se aplique às fases do projeto (enVision, onboard, valor da unidade)</li><li>Não incluir esses OKRs no OKRs existente</li></ul>|
> |A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte a portabilidade de números de telefone com antecedência (registro de atendimento ao cliente, detalhes de cobrança, carta de autorização)</li><li>Ajustar a linha do tempo do projeto para acomodar o tempo de retorno do número de telefone portando execução</li><li>Comunicar o uso de novos números de conferência de discagem para os participantes externos</li><li>Usar números de telefone temporários com a manipulação de identificação de chamadas</li></ul>|
> |Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar o Microsoft Teams como uma plataforma moderna de comunicação e colaboração, realize uma avaliação de prontidão de rede para sites em escopo do projeto</li></ul>|
> |Configuração do SBC|Alto|Alto|Alto|<ul><li>Antes de implementar o Teams como substituto para o PBX existente, confirme que você pode atender todos os requisitos de configuração de SBC</li><li>Confirme se os recursos de suporte do SBC têm o conjunto de habilidades apropriado para configurar o SBC para roteamento direto</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Quais são a sua organização&#39;s OKRs e KSIs?</li><li>Quais riscos você identificou relevantes para a implementação da conferência de áudio em sua organização? Quais são os planos de mitigação para os riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação de planos de chamada em sua organização? Quais são os planos de mitigação para os riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação de roteamento direto na sua organização? Quais são os planos de mitigação para os riscos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente o OKRs e o KSIs e estabeleça o registro de riscos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Estabelecer um Comitê de direcionamento

Um Comitê de direcionamento é um grupo regulador de principais interessados e líderes de projeto que se reuniram para orientar um projeto ou programa para seus resultados comerciais definidos. O Comitê de direcionamento não é responsável ** diretamente pela entrega do projeto, mas sim o *que* o projeto oferece à empresa.

Cada projeto requer uma visão e uma compromisso acordados. Para entregar os resultados desejados do projeto, a visão deve ser claramente definida, e ele precisa ser monitorado e mantido. Isso se torna a responsabilidade do Comitê de direcionamento: para impulsionar decisões, aconselhar, fornecer supervisão estratégica, servir como defensores da organização para as iniciativas do projeto e, quando necessário, remover bloqueadores.

Sua organização deve colocar um pensamento significativo na formação do Comitê de direcionamento. O Comitê deve garantir que o projeto atinja os objetivos de negócios que você definiu para atender às mudanças em toda a organização, se reunir periodicamente para discutir o pulso atual do projeto e ajudar a desproteger quaisquer obstáculos encontrados ao longo do propósito.

O Comitê deve definir seu compromisso para incluir alguns objetivos importantes:

-   Mantenha um forte alinhamento entre a equipe do projeto e o patrocinador executivo ou a liderança executiva.

-   Dê uma percepção do status do projeto para o patrocinador executivo ou liderança executiva.

-   Permita que o patrocinador executivo ou a equipe de liderança executiva forneça a direção e a entrada para o projeto e garanta que ele se alinhe às principais metas comerciais, ajustando planos de projeto, resultados de chave objetiva (OKRs) e outras atividades do projeto.

O Comitê de direcionamento se reúne em um intervalo recorrente durante o ciclo de vida de um projeto para garantir o alinhamento entre a liderança organizacional e a equipe do projeto. Essa reunião crítica garante que a direção do projeto tenha o suporte total da liderança e incorpora qualquer comentário oferecido pela liderança ao projeto para impulsionar o sucesso. O Comitê usa essas reuniões para obter informações sobre o status do projeto e para:

-   Concorde com os resultados dos negócios que se alinham ao business case e para garantir que o projeto seja direcionado à entrega desses resultados.

-   Verifique e aprove o projeto para a precisão e a conformidade com o business case.

-   Revise e verifique se as alterações feitas no business case podem afetar os resultados definidos.

-   Tome decisões estratégicas sobre a priorização dos resultados do projeto e aprove os resultados provisórios.

-   Identifique, gerencie e atenue falhas, riscos e problemas em que a influência adicional é necessária do Comitê.

-   Reúna o suporte do patrocinador executivo ou da equipe de liderança executiva para problemas que exigem escalonamento, priorização e resolução de qualquer conflito entre unidades de negócios interessadas. 

-   Forneça feedback formal e recomendações à liderança executiva, ao Conselho Consultivo de mudança ou a outros participantes de negócios e de ti, conforme aplicável.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Decida se um Comitê de direcionamento é necessário para a sua organização.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Identifique os membros do Comitê de direcionamento.</li><li>Agendar reuniões do Comitê de direcionamento.</li><li>Prepare-se para as reuniões do Comitê de direcionamento.</li><li>Mantenha as reuniões do Comitê de direcionamento.</li><li>Tome medidas com base na entrada de reunião do Comitê de direção.</li></ul>|

Orientações detalhadas adicionais sobre como operar um Comitê de direcionamento adequado podem ser encontradas no [Guia do Comitê de orientação](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->