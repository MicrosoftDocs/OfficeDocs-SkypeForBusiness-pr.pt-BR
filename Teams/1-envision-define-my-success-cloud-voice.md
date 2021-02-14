---
title: Audioconferência, planos de chamada ou roteamento direto
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definindo o sucesso para a implantação de Audioconferência, Sistema de Telefonia com Planos de Chamada ou Roteamento Direto do Sistema de Telefonia para sua organização.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 94430052082d523861ed4a938e0e0b02b70049f9
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610980"
---
# <a name="define-my-success"></a>Definir meu sucesso

Este artigo apresenta uma visão geral dos requisitos para definir o sucesso para a implantação de AudioConferência, Sistema de Telefonia com Planos de Chamada ou Roteamento Direto do Sistema de Telefonia para sua organização. Ao definir corretamente a aparência de sucesso, você pode medir seus resultados à medida que avança em sua implantação e verificar se os resultados obtidos são os que você queria.

<!--ENDOFSECTION-->

A **AudioConferência** fornece às organizações pontos de entrada adicionais para qualquer reunião (ad hoc ou agendada), permitindo que os participantes da reunião in join via PSTN (rede telefônica pública comutado) discando usando telefones fixos tradicionais, PBX (private branch exchange) ou celulares. Isso é útil quando o organizador ou os participantes não estão na frente de um computador ou quando as conexões de dados não estão disponíveis ou não são confiáveis para dar suporte a comunicações de voz, como em uma área remota com cobertura de dados móveis irregulares, ou conectadas a um serviço público gratuito de Wi-Fi com largura de banda limitada ou quando os participantes da reunião preferem discar para a reunião usando um ponto de extremidade de telefonia que seja facilmente acessível a eles.

**O Sistema telefônico com** planos de chamada ("Planos de Chamada") oferece às organizações uma maneira de modernizar seu local de trabalho, permitindo que os usuários façam chamadas telefônicas relacionadas à empresa a partir de seus computadores e dispositivos móveis. A modernização do local de trabalho pode fazer parte de qualquer número de cenários — uma implementação de trabalho baseada em atividades, uma mudança de escritório principal, uma atualização de ajuste do office, a rescisão de uma solução PBX herdada, a conclusão de um contrato de provedor de serviços PSTN e assim por diante. Com os Planos de Chamada, a Microsoft facilita a conectividade com o PSTN.

O Roteamento Direto do Sistema telefônico ("Roteamento **Direto")** oferece às organizações os mesmos benefícios listados acima para Planos de Chamada, exceto que a conectividade PSTN é facilitada por um provedor de terceiros em vez da Microsoft. Isso permite a implantação em países em que os Planos de Chamada não estão disponíveis ou em implantações em que um contrato de provedor de serviços PSTN existente precisa ser mantido ou a interoperabilidade com determinados sistemas locais é necessária. Um cenário adicional a ser considerado Roteamento Direto é a interoperabilidade do sistema de telefonia. Enquanto os usuários estão sendo transitivos para Chamada no Teams, alguns usuários podem permanecer em PBXs herdados. O Roteamento Direto permite que ambos os casos de uso coexistam. O tráfego de chamada entre os usuários em sistemas herdáveis e os usuários do Teams permanecem dentro da organização.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso comercial para Audioconferência, Planos de Chamada ou Roteamento Direto

Para começar, os principais participantes do projeto precisam definir casos de uso comercial que suportam a implementação de Audioconferência, Planos de Chamada ou Roteamento Direto.

Os casos de uso empresarial devem definir e documentar os resultados de negócios esperados e mensuráveis e incluir o seguinte:

-   Descrição do processo comercial atual

-   Desafios com o processo comercial existente

-   Como a tecnologia pode ajudar a superar esses desafios

-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para Audioconferência:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.|
> |**Desafios com os processos comerciais existentes**<br>A Contoso gasta aproximadamente US$ 1 milhão por ano para o serviço de conferência PSTN atual, com 75% do custo incorrido para reuniões internas. O uso de pontos de extremidade de telefonia tradicionais para ingressar nas reuniões hospedadas pelo serviço de conferência PSTN não está alinhado com o plano para que a organização adote o Teams como uma plataforma moderna de comunicação e colaboração.|
> |**Como a tecnologia pode superar esses desafios**<br>Com a adoção do Microsoft Teams como uma plataforma moderna de comunicação e colaboração, os usuários internos devem ingressar principalmente em reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião. O serviço de Audioconferência estará disponível para dar suporte a participantes externos ou para dar suporte a situações em que o uso de áudio do computador não seja favorável para os participantes internos.|
> |**Resultados comerciais esperados e mensuráveis**<br>A mudança para o Teams como uma plataforma moderna de comunicação e colaboração, combinada com o serviço de Audioconferência, reduzirá significativamente o custo para oferecer o serviço de conferência PSTN.|

<br>

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para Planos de Chamada:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho de escritório da Contoso inclui um telefone de mesa para cada mesa. Cada funcionário recebe um número de telefone de discagem direta para dentro (DID). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados ao PSTN por meio de um tronco de protocolo SIP. Os funcionários só podem fazer e receber chamadas telefônicas em seus telefones de mesa atribuídos.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones desktop mostra que apenas 10% dos telefones desktop são usados ativamente, com o restante configurado para encaminhar chamadas para telefones celulares ou para ligar simultaneamente para celulares. Manter o sistema PBX existente e os telefones de mesa associados contribui para 20% do custo de serviço de telefonia mensal da Contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>Os Planos de Chamada permitirão que o computador pessoal de um usuário receba e coloque chamadas telefônicas pela rede de dados aproveitando o aplicativo nativo do Microsoft Teams. Isso remove a necessidade de distribuição e manutenção de telefones desktop e abre a oportunidade de desativação do sistema PBX existente, pois o serviço de telefonia pode ser entregue por meio da nuvem pela rede sem dependência em um sistema telefônico tradicional.|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e a desativação do PBX herdável e dos telefones de mesa oferecerão uma redução de 20% nas despesas mensais de serviço de telefonia. Os Planos de Chamada simplificarão os espaços de trabalho do escritório, permitindo que a Contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia antecipado.|

<br>

> [!TIP]
> Veja a seguir um exemplo de um caso de uso comercial concluído para Roteamento Direto:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho de escritório da Contoso inclui um telefone de mesa para cada mesa. Cada funcionário recebe um número de telefone de discagem direta para dentro (DID). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados ao PSTN por meio de um tronco de protocolo SIP. Os funcionários só podem fazer e receber chamadas telefônicas em seus telefones de mesa atribuídos.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones desktop mostra que apenas 10% dos telefones desktop são usados ativamente, com o restante configurado para encaminhar chamadas para telefones celulares ou para ligar simultaneamente para celulares. Manter o sistema PBX existente e os telefones de mesa associados contribui para 20% do custo de serviço de telefonia mensal da Contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>O contrato do provedor de tronco SIP foi assinado recentemente e ficará em uso por três anos. O Roteamento Direto permite que a conectividade PSTN seja fornecida pelo provedor de tronco SIP e também permitirá que o computador pessoal do usuário receba e coloque chamadas telefônicas pela rede de dados aproveitando o aplicativo nativo do Microsoft Teams. Isso remove a necessidade de distribuição e manutenção de telefones da área de trabalho e abre a oportunidade de desativação do sistema PBX existente, mantendo uma área de controle de borda de sessão (SBC) limitada.|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e a desativação do PBX herdável e dos telefones de mesa oferecerão uma redução de 20% nas despesas mensais de serviço de telefonia. O Roteamento Direto simplificará os espaços de trabalho do escritório, permitindo que a Contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia antecipado.|

Além de definir seus casos de uso comercial, para definir os limites do projeto, você deve buscar a clareza:

-   **Escopo organizacional:** A implementação de Audioconferência, Planos de Chamada ou Roteamento Direto pode abranger toda a organização ou apenas unidades de negócios específicas.

-   **Linha do tempo do projeto:** A linha do tempo específica que o projeto executará.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Pontos de decisão|<ul><li>Quais são todos os casos de uso comercial para Audioconferência que você pode identificar em sua organização?</li><li>Quais são todos os casos de uso comercial para Planos de Chamada que você pode identificar em sua organização?</li><li>Quais são todos os casos de uso comercial do Roteamento Direto que você pode identificar em sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os casos de uso comercial para Audioconferência para sua organização.</li><li>Documente todos os casos de uso comercial para Planos de Chamada para sua organização.</li><li>Documente todos os casos de uso comercial para Roteamento Direto para sua organização.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas

Os casos de uso comercial definidos na etapa anterior incluem um escopo organizacional para a audioconferência, planos de chamada ou implementação de Roteamento Direto. Com base nisso, você pode concluir a matriz abrangente de participantes para incluir as pessoas certas a se envolverem no projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
> 
> |Função  |Descrição  |Nome, informações de contato, localização  |
> |---------|---------|---------|
> |Patrocinador executivo do projeto|<ul><li>Tome autoridade e responsabilidade máximas para o projeto e entrega nos objetivos do projeto.</li><li>Ajude a resolver problemas escalonados pelo Líder do Projeto.</li><li>Patrocine a comunicação dentro da empresa sobre as metas do projeto.</li><li>Tomar as principais decisões estratégicas.</li><li>Garanta a disponibilidade de recursos e orçamento necessários.</li><li>Liderar avaliações de negócios trimestrais (QBRs).</li><li>Impulsionar a compra e o suporte dos esforços de campanha de reconhecimento.</li><li>Servir como o Patrocinador do Projeto para a adoção do programa.</li></ul>|TBA|
> |Líder de projeto|<ul><li>Gerencie e gerencie a equipe do projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidas no projeto.</li><li>Seja responsável por criar e gerenciar planos de projeto para atender aos principais resultados trimestrais.</li><li>Resolver problemas multifuncionais.</li><li>Forneça atualizações regulares aos patrocinadores do projeto.</li><li>Incorporar aspectos de adoção ao plano de projeto todo.</li><li>Leve em conta as Avaliações Comerciais e Operacionais mensais (MBRs), contribua com QBRs.</li></ul>|TBA|
> |Líder/arquiteto de colaboração|<ul><li>Execute na estratégia de colaboração definida pelos executivos da empresa.</li><li>Analise e escolha produtos de colaboração que atendem às metas de negócios da empresa.</li><li>Operações de design para produtos de colaboração.</li><li>Definir modelos de operação e suporte.</li><li>Contribua com avaliações de negócios mensais e trimestrais.</li></ul>|TBA|
> |Consultor|<ul><li>Ser responsável pelos serviços de configuração</li><li>Contribua com a arquitetura geral de soluções.</li></ul>|TBA|
> |Gerente de projetos|<ul><li>Desenvolva e mantenha o plano do projeto.</li><li>Gerencie as entregas do projeto de acordo com o plano e o orçamento do projeto.</li><li>Grave e gerencie problemas do projeto, incluindo escalonamentos.</li><li>Realizar chamadas em standup semanais.</li><li>Forneça e forneça atualizações para os patrocinadores executivos do projeto.</li><li>Trabalhe com o arquiteto para definir a abordagem de gerenciamento de alterações e os planos de comunicação.</li></ul>|TBA|
> |Especialista em adoção/gerenciamento de mudanças|<ul><li>Forneça informações durante a fase descoberta nos processos de adoção e treinamento.</li><li>Participe do workshop de estratégia de adoção.</li><li>Desenvolva e tome a responsabilidade pela estratégia de adoção.</li><li>Desenvolva e execute o plano de comunicação.</li><li>Fornecer treinamentos aos usuários.</li><li>Coletar comentários e realizar pesquisas.</li></ul>|TBA|
> |Líder de rede|<ul><li>Forneça informações durante a fase descoberta no design de rede.</li><li>Participe do planejamento durante o workshop de fases de Previsão.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>|TBA|
> |Líder de segurança|<ul><li>Forneça informações durante a fase descoberta em processos e design de segurança.</li><li>Participe do planejamento durante o workshop de fases de Previsão.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>|TBA|
> |Líder de telefonia|<ul><li>Forneça informações durante a fase descoberta no design de telefonia.</li><li>Participe do planejamento durante o workshop de fases de Previsão.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>|TBA|
> |Líder de desktop|<ul><li>Forneça informações durante a fase descoberta para os clientes e o processo de atualização.</li><li>Participe do planejamento durante o workshop de Previsão.</li><li>Coordene o trabalho da equipe da área de trabalho durante a execução do projeto.</li></ul>|TBA|
> |Líder de suporte/suporte técnico|<ul><li>Forneça informações durante a fase descoberta em modelos operacionais e de suporte.</li><li>Participe do planejamento durante o workshop de fases de Previsão.</li><li>Participe do planejamento de modelo de suporte.</li><li>Coordene o trabalho das equipes de suporte e dos recursos durante a execução do projeto.</li></ul>|TBA|
> |Representantes das unidades de negócios|<ul><li>Contribua com materiais e guias de adoção baseados no usuário.</li><li>Contribua com e revise casos de uso comercial.</li></ul>|TBA|
> |Líder de implantação|<ul><li>Certifique-se de que os pré-requisitos de implantação sejam atendidos.</li><li>Envolva os recursos para se envolver nas atividades de fase de integração.</li><li>Participe de reuniões para revisar e preparar relatórios sobre o status da implantação.</li></ul>|TBA|
> |Administradores de TI|<ul><li>Ajude com o planejamento e a execução de testes. Esta função é para profissionais de IT.</li></ul>|TBA|
> |Proprietário do serviço|<ul><li>Seja responsável pela operação da Audioconferência, dos Planos de Chamada ou do serviço de Roteamento Direto, tudo.</li><li>Possui o serviço audioconferência, planos de chamada ou roteamento direto.</li></ul>|TBA|
> |Defensores da qualidade|<ul><li>Qualidade da unidade, confiabilidade e comentários do usuário.</li><li>Identifique tendências de qualidade e conduza a correção com as respectivas equipes.</li><li>Reporte por meio do comitê de direção de volta à liderança.</li><li>Relatório sobre qualidade, confiabilidade e sentimentos do usuário por meio do Rate My Call e Net Promoter Score.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Quem preencherá cada função de stakeholder principal para sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os principais participantes e comunique as responsabilidades e as expectativas da função a cada indivíduo atribuído.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir OKRs, KSIs e riscos

Com os participantes do projeto reunidos, você pode traduzir casos de uso empresarial, escopo organizacional e linhas do tempo do projeto em objetivos e principais resultados (OKRs), e as medidas de sucesso do projeto podem ser definidas como uma lista de KSIs (indicadores chave de sucesso).

A participação total dos participantes do projeto na definição de OKRs e KSIs é essencial para ajudar a garantir que eles sintam uma noção de propriedade e alinhem essas medidas de sucesso aos requisitos de negócios organizacionais.

AS OKRs contêm os objetivos definidos no início do projeto e você define resultados principais mensuráveis trimestralmente. Você revisa os principais resultados mensais para controlar o status do projeto geral e, com base no andamento, ajusta os planos trimestrais conforme necessário.

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de Audioconferência podem ser referenciados abaixo:
> <br>
> 
> **Visão: aumentar a produtividade maximizando os investimentos do Microsoft 365 ou do Office 365**
> 
> |Objetivos  |Principais resultados  |Para fazer  |
> |---------|---------|---------|
> |Implantar Audioconferência no Teams até o final do ano fiscal de 2018|1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018|2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de Planos de Chamada podem ser referenciados abaixo:
> <br>
> 
> **Visão: aumentar a produtividade maximizando os investimentos do Microsoft 365 ou do Office 365**
> 
> |Objetivos  |Principais resultados  |Para fazer  |
> |---------|---------|---------|
> |Implantar Planos de Chamada em filiais europeias até o final do ano fiscal de 2018|FY18Q3: Implantar planos de chamada no escritório de Londres|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Desative o PBX herdado no escritório de Londres até o final do ano fiscal de 2018|FY18Q4: Desative o PBX herdados no escritório de Londres|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|
> 
> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de Roteamento Direto podem ser referenciados abaixo:
> <br>
> 
> **Visão: aumentar a produtividade maximizando os investimentos do Microsoft 365 ou do Office 365**
> 
> |Objetivos  |Principais resultados  |Para fazer  |
> |---------|---------|---------|
> |Implantar o Roteamento Direto em filiais canadenses até o final do ano fiscal de 2018|FY18Q3: Implantar Roteamento Direto no office de Toronto|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Desative o PBX herdado no escritório de Toronto até o final do ano fiscal de 2018|FY18Q4: Desative o PBX herdados no escritório de Toronto|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

Os KSIs medem a qualidade e o sucesso dos principais resultados e complementam a natureza binária das OKRs (conquistadas ou não conquistadas) detalhando resultados bons e/ou ruins.

Ao definir KSIs, recomendamos que você use critérios "específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo" (SMART:

-   Específico: direcionar uma área específica para aprimoramento

-   Mensurável: quantificar ou pelo menos sugerir um indicador de progresso

-   Atribuível: especificar quem fará isso

-   Realista: estados quais resultados podem ser obtidos de forma realista, dados os recursos disponíveis

-   Tempo relacionado: especificar quando os resultados podem ser obtidos

> [!TIP]
> Este é um exemplo de KSI relevante para esse projeto:
> 
> |Tipo  |Pergunta e critérios do KSI  |Como foi mensurado  |Critérios de sucesso  |Mensurado  |Responsável  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adoção|A qualidade da chamada é igual ou melhor que a solução anterior|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Esquipe de Tecnologia da Informação|
> |Uso/adoção|O Microsoft Teams facilitou o processo de comunicação|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/adoção|Os usuários usam a solução ativamente|Relatórios do Microsoft 365, Painel de Qualidade da Chamada|80% dos usuários são usuários ativos diariamente|Diariamente|Equipe de gerenciamento de mudanças|
> |Uso/qualidade|A porcentagem de chamadas/conferências de má qualidade deve ser mínima|Painel de Qualidade da Chamada|< 5% de chamadas de má qualidade por mês|Diariamente|Esquipe de Tecnologia da Informação|
> |Uso/suporte|Eu sei como obter suporte técnico|Pesquisa|90% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/suporte|Estou satisfeito com a qualidade do suporte técnico|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após cada incidente|Esquipe de Tecnologia da Informação|
> |Financeiro|Redução dos minutos de conferência herdados|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Você precisa identificar os riscos comerciais como parte deste exercício e definir um plano de atenuação para cada risco identificado. Essas informações podem ser capturadas em um registro de riscos.

> [!TIP]
> Seu registro de risco pode ser documentado como exemplo abaixo:
> 
> |Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
> |---------|---------|---------|---------|---------|
> |A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas mescladas, crie uma OKR separada que se aplique às suas próprias fases de projeto (Previsão, Integração, Valor de Unidade)</li><li>Não inclua essas OKRs em OKRs existentes</li></ul>|
> |A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte à portagem de número de telefone com antecedência (registro de atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</li><li>Ajustar a linha do tempo do projeto para acomodar o tempo de resposta da execução da portagem de número de telefone</li><li>Comunicar o uso de novos números de conferência de discagem para os participantes externos</li><li>Usar números de telefone temporários com manipulação de ID de chamadas</li></ul>|
> |Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar o Teams como uma plataforma moderna de comunicação e colaboração, conduza uma avaliação de preparação de rede para sites no escopo do projeto</li></ul>|
> |Configuração SBC|Alto|Alto|Alto|<ul><li>Antes de implementar o Teams como substituto para o PBX existente, confirme que você pode atender a todos os requisitos de configuração SBC</li><li>Confirme se os recursos de suporte SBC têm as habilidades adequadas definidas para configurar o SBC para Roteamento Direto</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>O que sua organização&#39;okrs e KSIs?</li><li>Quais riscos você identificou relevantes para a implementação da Audioconferência em sua organização? Quais são os planos de redução dos riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação de Planos de Chamada em sua organização? Quais são os planos de redução dos riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação do Roteamento Direto em sua organização? Quais são os planos de redução dos riscos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente as OKRs e KSIs e estabeleça o registro de riscos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Criar um comitê de direção

Um comitê de orientação é um grupo que rege os principais participantes e líderes de projetos que foram unidos para orientar um projeto ou programa para seus resultados de negócios definidos. O comitê de direção não  é diretamente responsável pela  forma como o projeto é entregue, mas sim pelo que o projeto fornece para a empresa.

Cada projeto requer uma visão e um estatuto de acordo. Para fornecer os resultados que você deseja do projeto, a visão deve ser claramente definida e precisa ser monitorada e mantida. Isso se torna responsabilidade do comitê de direção: orientar decisões, aconselhar, fornecer supervisão estratégia, para servir como defensores da organização para as iniciativas do projeto e, quando necessário, remover bloqueadores.

Sua organização deve colocar um pensamento significativo na formação do comitê de direção. O comitê deve garantir que o projeto alcance os objetivos comerciais que você definiu para impulsionar as mudanças em toda a organização, reunir-se periodicamente para discutir o ritmo atual do projeto e ajudar a desbloquear quaisquer obstáculos encontrados ao longo do caminho.

O comitê deve definir seu estatuto para incluir alguns dos principais objetivos:

-   Mantenha um alinhamento forte entre a equipe do projeto e o patrocinador executivo ou a liderança executiva.

-   Forneça informações sobre o status do projeto ao patrocinador executivo ou à liderança executiva.

-   Permita que o patrocinador executivo ou a equipe de liderança executiva forneça direção e entrada para o projeto e garanta que ele esteja alinhado com metas comerciais abrangentes, ajustando planos de projeto, resultados de chave de objetivo (OKRs) e outras atividades do projeto.

O comitê de direção se reúne em um intervalo recorrente durante todo o tempo de vida de um projeto para garantir o alinhamento entre a liderança organizacional e a equipe do projeto. Esta reunião crítica garante que a direção do projeto tenha total suporte da liderança e incorpora todos os comentários fornecidos pela liderança no projeto para impulsionar o sucesso. O comitê usa essas reuniões para obter informações sobre o status do projeto e para:

-   Concordo com os resultados comerciais que se alinham com o caso comercial e para garantir que o projeto esteja indo para a entrega desses resultados.

-   Verifique e aprove o projeto para ter precisão e conformidade com o caso comercial.

-   Revise e verifique as alterações feitas no caso comercial que podem afetar quaisquer resultados definidos.

-   Tomar decisões estratégicas sobre a priorização de entregas de projetos e aprovar entregas provisórias.

-   Identifique, gerencie e reduza lacunas, riscos e problemas nos quais é necessária mais influencia do comitê.

-   Reúna o suporte do patrocinador executivo ou da equipe de liderança executiva para problemas que exigem escalonamento, priorização e resolução de conflitos entre unidades de negócios dos participantes. 

-   Forneça comentários formais e recomendações à liderança executiva, ao conselho de avisos de mudança ou a outros participantes de negócios e de IT, conforme aplicável.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Decida se um comitê de direção é necessário para sua organização.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Identifique os membros do comitê de direção.</li><li>Agende reuniões do comitê de direção.</li><li>Prepare-se para reuniões do comitê de direção.</li><li>Realizar reuniões do comitê de direção.</li><li>Tome medidas com base na entrada da reunião do comitê de direção.</li></ul>|

Orientações detalhadas adicionais sobre como operar um comitê de orientação adequado podem ser encontradas no guia [do comitê de orientação.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
