---
title: Audioconferência, Planos de Chamadas ou Roteamento Direto
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definindo o sucesso para a implantação da Audioconferência, Sistema de Telefonia com Planos de Chamadas ou Sistema de Telefonia Roteamento Direto para sua organização.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e669e0454f65ef4d3d5ecc0b4832b33201d2703
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011755"
---
# <a name="define-my-success"></a>Definir meu sucesso

Este artigo fornece uma visão geral dos requisitos para definir o sucesso para a implantação da Audioconferência, Sistema de Telefonia com Planos de Chamadas ou Sistema de Telefonia Roteamento Direto para sua organização. Ao definir corretamente a aparência do sucesso, você pode medir seus resultados à medida que avança pela implantação e verificar se os resultados alcançados são os que você queria.

<!--ENDOFSECTION-->

A **Audioconferência** fornece às organizações pontos de entrada adicionais para qualquer reunião (ad hoc ou agendada) permitindo que os participantes da reunião participem por meio da PSTN (rede telefônica pública comutado) discando usando telefones fixos tradicionais, pbx (troca de filial privada) ou telefones celulares. Isso é útil quando o organizador ou os participantes não estão na frente de um computador ou quando as conexões de dados estão indisponíveis ou não confiáveis para dar suporte a comunicações de voz, como em uma área remota com cobertura de dados móveis irregulares, ou conectados a um serviço de Wi-Fi público gratuito com largura de banda limitada ou quando os participantes da reunião preferem discar para a reunião usando um ponto de extremidade de telefonia prontamente acessível a eles.

**Sistema de Telefonia com Planos** de Chamadas ("Planos de Chamadas") oferece às organizações uma maneira de modernizar seu local de trabalho, permitindo que os usuários façam chamadas telefônicas relacionadas aos negócios a partir de seus computadores e dispositivos móveis. A modernização do local de trabalho pode fazer parte de qualquer número de cenários, uma implementação de trabalho baseada em atividade, uma grande movimentação de escritório, uma atualização de ajuste do office, a retirada de uma solução PBX herdada, a conclusão de um contrato de provedor de serviços PSTN e assim por diante. Com planos de chamada, a Microsoft facilita a conectividade com o PSTN.

Sistema de Telefonia Roteamento Direto **("Roteamento Direto")** fornece às organizações os mesmos benefícios listados acima para Planos de Chamadas, exceto que a conectividade PSTN é facilitada por um provedor de terceiros, em vez da Microsoft. Isso permite a implantação em países onde planos de chamada não estão disponíveis ou em implantações em que um contrato de provedor de serviços PSTN existente precisa ser mantido ou a interoperabilidade com determinados sistemas locais é necessária. Um cenário adicional a ser considerado Roteamento Direto é a interoperabilidade do sistema de telefonia. Enquanto os usuários estão sendo transidos para Chamar no Teams, alguns usuários podem permanecer em PBXs herdados. O Roteamento Direto permite que ambos usem casos para coexistir. O tráfego de chamada entre os usuários em sistemas herdado e Teams os usuários permanecem dentro da organização.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir casos de uso comercial para Audioconferência, Planos de Chamadas ou Roteamento Direto

Para começar, os principais participantes do projeto precisam definir casos de uso comercial que suportam a implementação de Audioconferência, Planos de Chamadas ou Roteamento Direto.

Os casos de uso comercial devem definir e documentar os resultados de negócios esperados e mensuráveis e incluir o seguinte:

-   Descrição do processo de negócios atual

-   Desafios com o processo de negócios existente

-   Como a tecnologia pode ajudar a superar esses desafios

-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

> [!TIP]
> Veja a seguir um exemplo de caso de uso comercial concluído para Audioconferência:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.|
> |**Desafios com os processos comerciais existentes**<br>A Contoso gasta aproximadamente US$ 1 milhão por ano para o serviço de conferência PSTN atual, com 75% do custo incorrido para reuniões internas. O uso de pontos de extremidade de telefonia tradicionais para ingressar nas reuniões hospedadas pelo serviço de conferência PSTN não está alinhado com o plano para a organização adotar o Teams como uma plataforma moderna de comunicação e colaboração.|
> |**Como a tecnologia pode superar esses desafios**<br>Com a adoção do Microsoft Teams como uma plataforma moderna de comunicação e colaboração, espera-se que os usuários internos participem principalmente de reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião. O serviço de Audioconferência estará disponível para dar suporte a participantes externos ou para suportar situações em que o uso de áudio de computador não seja favorável para os participantes internos.|
> |**Resultados comerciais esperados e mensuráveis**<br>A mudança para Teams como uma plataforma moderna de comunicação e colaboração, combinada com o serviço de Audioconferência, reduzirá consideravelmente o custo para fornecer o serviço de conferência PSTN.|

<br>

> [!TIP]
> Veja a seguir um exemplo de caso de uso comercial concluído para Planos de Chamada:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do escritório da Contoso inclui um telefone de área de trabalho para cada mesa. Cada funcionário recebeu um número de telefone DID (discagem direta para dentro). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados ao PSTN por meio de um tronco SIP (protocolo de iniciação de sessão). Os funcionários só podem fazer e receber chamadas telefônicas em seus telefones de área de trabalho atribuídos.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones da área de trabalho mostra que apenas 10% dos telefones da área de trabalho são usados ativamente, com o restante configurado para encaminhar chamadas para telefones celulares ou para tocar simultaneamente em telefones celulares. A manutenção do sistema PBX existente e dos telefones de área de trabalho associados contribui para 20% do custo mensal do serviço de telefonia da Contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>Os Planos de Chamadas permitirão que o computador pessoal do usuário receba e coloque chamadas telefônicas pela rede de dados aproveitando o aplicativo Microsoft Teams nativo. Isso remove a necessidade de lançar e manter telefones de área de trabalho e abre a oportunidade de desativação do sistema PBX existente, pois o serviço de telefonia pode ser entregue por meio da nuvem pela rede sem dependência de um sistema de telefonia tradicional.|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e o descomissionamento de telefones de área de trabalho e PBX herdáveis oferecerão uma redução de 20% nas despesas mensais do serviço de telefonia. Os Planos de Chamada simplificarão os espaços de trabalho do office, permitindo que a Contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia inicial.|

<br>

> [!TIP]
> Veja a seguir um exemplo de caso de uso comercial concluído para Roteamento Direto:
> 
> |         |
> |---------|
> |**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do escritório da Contoso inclui um telefone de área de trabalho para cada mesa. Cada funcionário recebeu um número de telefone DID (discagem direta para dentro). Os telefones da área de trabalho estão conectados a um sistema PBX e conectados ao PSTN por meio de um tronco SIP (protocolo de iniciação de sessão). Os funcionários só podem fazer e receber chamadas telefônicas em seus telefones de área de trabalho atribuídos.|
> |**Desafios com os processos comerciais existentes**<br>A análise de uso dos telefones da área de trabalho mostra que apenas 10% dos telefones da área de trabalho são usados ativamente, com o restante configurado para encaminhar chamadas para telefones celulares ou para tocar simultaneamente em telefones celulares. A manutenção do sistema PBX existente e dos telefones de área de trabalho associados contribui para 20% do custo mensal do serviço de telefonia da Contoso.|
> |**Como a tecnologia pode superar esses desafios**<br>O contrato de provedor de tronco SIP foi assinado recentemente e ficará no local por três anos. O Roteamento Direto permite que a conectividade PSTN seja fornecida pelo provedor de tronco SIP e também permitirá que o computador pessoal do usuário receba e coloque chamadas telefônicas pela rede de dados aproveitando o aplicativo Microsoft Teams nativo. Isso remove a necessidade de lançar e manter telefones de área de trabalho e abre a oportunidade de descompactar o sistema PBX existente, mantendo um espaço limitado no SBC (controlador de borda de sessão local).|
> |**Resultados comerciais esperados e mensuráveis**<br>A remoção dos requisitos de manutenção e o descomissionamento de telefones de área de trabalho e PBX herdáveis oferecerão uma redução de 20% nas despesas mensais do serviço de telefonia. O Roteamento Direto simplificará os espaços de trabalho do office, permitindo que a Contoso expanda suas operações estabelecendo novos escritórios com custos mínimos de telefonia inicial.|

Além de definir seus casos de uso comercial, para definir os limites do projeto, você deve ter o objetivo de impulsionar a clareza ao redor:

-   **Escopo organizacional:** A implementação de Audioconferência, Planos de Chamadas ou Roteamento Direto pode abranger toda a organização ou apenas unidades de negócios específicas.

-   **Project linha do tempo:** A linha do tempo específica que o projeto executará.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Pontos de decisão|<ul><li>Quais são todos os casos de uso comercial para Audioconferência que você pode identificar em sua organização?</li><li>Quais são todos os casos de uso comercial para Planos de Chamada que você pode identificar em sua organização?</li><li>Quais são todos os casos de uso comercial para Roteamento Direto que você pode identificar em sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os casos de uso comercial para Audioconferência para sua organização.</li><li>Documente todos os casos de uso comercial para Planos de Chamada para sua organização.</li><li>Documente todos os casos de uso comercial para Roteamento Direto para sua organização.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas

Os casos de uso comercial definidos na etapa anterior incluem um escopo organizacional para a implementação de Audioconferência, Planos de Chamadas ou Roteamento Direto. Com base nisso, você pode concluir a matriz abrangente de stakeholders para incluir as pessoas certas a envolver no projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
> 
> |Função  |Descrição  |Nome, informações de contato, localização  |
> |---------|---------|---------|
> |Patrocinador executivo do projeto|<ul><li>Leve autoridade e responsabilidade final para o projeto e a entrega nos objetivos do projeto.</li><li>Ajude a resolver problemas escalonados pelo Project Lead.</li><li>Patrocine a comunicação dentro da empresa sobre as metas do projeto.</li><li>Tomar decisões estratégicas importantes.</li><li>Garantir a disponibilidade de recursos e orçamento necessários.</li><li>Conduzir avaliações de negócios trimestrais (QBRs).</li><li>Impulsionar a compra e o suporte dos esforços de campanha de conscientização.</li><li>Sirva como o Project patrocinador para a adoção do programa.</li></ul>|TBA|
> |Líder de projeto|<ul><li>Gerenciar e liderar a equipe de projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidas no projeto.</li><li>Ser responsável pela criação e gerenciamento de planos de projeto para atender aos principais resultados trimestrais.</li><li>Resolver problemas multifuncionais.</li><li>Forneça atualizações regulares aos patrocinadores do projeto.</li><li>Incorpore aspectos de adoção ao plano de projeto all-up.</li><li>Conduzir avaliações mensais de Negócios e Operacionais (MBRs), contribuir para QBRs.</li></ul>|TBA|
> |Líder/arquiteto de colaboração|<ul><li>Execute na estratégia de colaboração definida pelos executivos da empresa.</li><li>Analise e escolha produtos de colaboração que atendem às metas de negócios da empresa.</li><li>Projetar operações para produtos de colaboração.</li><li>Definir modelos de operação e suporte.</li><li>Contribua com avaliações de negócios mensais e trimestrais.</li></ul>|TBA|
> |Consultor|<ul><li>Ser responsável pelos serviços de configuração</li><li>Contribuir para a arquitetura geral da solução.</li></ul>|TBA|
> |Gerente de projetos|<ul><li>Desenvolva e mantenha o plano de projeto.</li><li>Gerenciar os produtos do projeto em linha com o plano de projeto e o orçamento.</li><li>Grave e gerencie problemas do projeto, incluindo escalonamentos.</li><li>Conduza chamadas de stand-up semanais.</li><li>Entre em contato com e forneça atualizações para patrocinadores executivos do projeto.</li><li>Trabalhe com o arquiteto para definir a abordagem de gerenciamento de alterações e planos de comunicação.</li></ul>|TBA|
> |Especialista em adoção/gerenciamento de mudanças|<ul><li>Forneça entrada durante a fase Descoberta em processos de adoção e treinamento.</li><li>Participe do workshop de estratégia de adoção.</li><li>Desenvolver e assumir a responsabilidade pela estratégia de adoção.</li><li>Desenvolva e execute o plano de comunicação.</li><li>Fornecer treinamentos aos usuários.</li><li>Coletar comentários e realizar pesquisas.</li></ul>|TBA|
> |Líder de rede|<ul><li>Forneça entrada durante a fase descoberta no design de rede.</li><li>Participe do planejamento durante o workshop de fases do Envision.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>|TBA|
> |Líder de segurança|<ul><li>Forneça entrada durante a fase descoberta em processos e design de segurança.</li><li>Participe do planejamento durante o workshop de fases do Envision.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>|TBA|
> |Líder de telefonia|<ul><li>Forneça entrada durante a fase Descoberta no design de telefonia.</li><li>Participe do planejamento durante o workshop de fases do Envision.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>|TBA|
> |Líder de desktop|<ul><li>Forneça entrada durante a fase Descoberta nos clientes e no processo de atualização.</li><li>Participe do planejamento durante o workshop Envision.</li><li>Coordene o trabalho da equipe de área de trabalho durante a execução do projeto.</li></ul>|TBA|
> |Líder de suporte/suporte técnico|<ul><li>Forneça entrada durante a fase descoberta em modelos operacionais e de suporte.</li><li>Participe do planejamento durante o workshop de fases do Envision.</li><li>Participe do planejamento do modelo de suporte.</li><li>Coordene o trabalho de equipes de suporte e recursos durante a execução do projeto.</li></ul>|TBA|
> |Representantes das unidades de negócios|<ul><li>Contribuir com guias e materiais de adoção baseados no usuário.</li><li>Contribuir e revisar casos de uso comercial.</li></ul>|TBA|
> |Líder de implantação|<ul><li>Certifique-se de que os pré-requisitos de implantação sejam atendidos.</li><li>Envolva os recursos a serem envolvidos nas atividades de fase de integração.</li><li>Participe de reuniões para revisar e preparar relatórios sobre o status da implantação.</li></ul>|TBA|
> |Administradores de TI|<ul><li>Ajude no planejamento e execução de testes. Essa função é para profissionais de IT.</li></ul>|TBA|
> |Proprietário do serviço|<ul><li>Seja responsável pela operação da Audioconferência, planos de chamadas ou serviço de Roteamento Direto, tudo em cima.</li><li>Possui o serviço audioconferência, planos de chamadas ou roteamento direto.</li></ul>|TBA|
> |Defensores da qualidade|<ul><li>Qualidade da unidade, confiabilidade e comentários do usuário.</li><li>Identifique tendências de qualidade e a correção de unidade com as respectivas equipes.</li><li>Reporte por meio do comitê de direção de volta à liderança.</li><li>Relatório sobre a qualidade, a confiabilidade e o sentimento do usuário por meio do Rate My Call e Net Promoter Score.</li></ul>|TBA|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Quem preencherá cada função de stakeholder principal para sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente todos os principais participantes e comunique as responsabilidades e expectativas da função a cada indivíduo atribuído.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir OKRs, KSIs e riscos

Com os participantes do projeto reunidos, você pode converter casos de uso empresarial, escopo organizacional e cronogramas de projeto em objetivos e principais resultados (OKRs), e as medidas de sucesso do projeto podem ser definidas como uma lista de indicadores de sucesso principais (KSIs).

A participação completa dos participantes do projeto na definição de OKRs e KSIs é essencial para ajudar a garantir que eles sintam uma noção de propriedade e alinhem essas medidas de sucesso aos requisitos de negócios organizacionais.

Os OKRs contêm os objetivos definidos no início do projeto e definem resultados importantes mensuráveis trimestralmente. Você revisa os principais resultados mensais para controlar o status do projeto geral e, com base no progresso, ajusta os planos trimestrais conforme necessário.

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de Audioconferência podem ser referenciados abaixo:
> <br>
> 
> **Visão: aumentar a produtividade maximizando os investimentos do Microsoft 365 ou office 365**
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
> **Visão: aumentar a produtividade maximizando Microsoft 365 ou Office 365 investimentos**
> 
> |Objetivos  |Principais resultados  |Para fazer  |
> |---------|---------|---------|
> |Implantar planos de chamada em filiais europeias até o final do ano fiscal de 2018|FY18Q3: Implantar planos de chamada no escritório de Londres|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Desativação do PBX herdado no escritório de Londres até o final do ano fiscal de 2018|FY18Q4: PBX herdados de desativação no escritório de Londres|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|
> 
> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de Roteamento Direto podem ser referenciados abaixo:
> <br>
> 
> **Visão: aumentar a produtividade maximizando Microsoft 365 ou Office 365 investimentos**
> 
> |Objetivos  |Principais resultados  |Para fazer  |
> |---------|---------|---------|
> |Implantar Roteamento Direto em filiais canadenses até o final do ano fiscal de 2018|FY18Q3: Implantar Roteamento Direto no escritório de Toronto|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
> |Desativação do PBX herdado no escritório de Toronto até o final do ano fiscal de 2018|FY18Q4: PBX herdados de desativação no escritório de Toronto|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

Os KSIs medem a qualidade e o sucesso dos principais resultados e complementam a natureza binária das OKRs (alcançadas ou não atingidas) detalhando os resultados bons e/ou ruins.

Ao definir KSIs, recomendamos que você use critérios "específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo" (SMART) :

-   Específico: direcionar uma área específica para melhoria

-   Mensurável: quantificar ou, pelo menos, sugerir um indicador de progresso

-   Atribuível: especifique quem fará isso

-   Realista: estado quais resultados podem ser alcançados realisticamente, considerando os recursos disponíveis

-   Relacionado ao tempo: especifique quando os resultados podem ser alcançados

> [!TIP]
> Este é um exemplo de KSI relevante para esse projeto:
> 
> |Tipo  |Pergunta e critérios do KSI  |Como foi mensurado  |Critérios de sucesso  |Mensurado  |Responsável  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adoção|A qualidade da chamada é igual ou melhor que a solução anterior|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Esquipe de Tecnologia da Informação|
> |Uso/adoção|O Microsoft Teams facilitou o processo de comunicação|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/adoção|Os usuários usam a solução ativamente|Microsoft 365 relatórios, Painel de Qualidade de Chamada|80% dos usuários são usuários ativos diariamente|Diariamente|Equipe de gerenciamento de mudanças|
> |Uso/qualidade|A porcentagem de chamadas/conferências de má qualidade deve ser mínima|Painel de Qualidade da Chamada|< 5% de chamadas de má qualidade por mês|Diariamente|Esquipe de Tecnologia da Informação|
> |Uso/suporte|Eu sei como obter suporte técnico|Pesquisa|90% dos usuários concordam ou concordam fortemente|Após a habilitação e trimestralmente|Equipe de gerenciamento de mudanças|
> |Uso/suporte|Estou satisfeito com a qualidade do suporte técnico|Pesquisa|80% dos usuários concordam ou concordam fortemente|Após cada incidente|Esquipe de Tecnologia da Informação|
> |Financeiro|Redução dos minutos de conferência herdados|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Você precisa identificar os riscos comerciais como parte desse exercício e definir um plano de mitigação para cada risco identificado. Essas informações podem ser capturadas em um registro de riscos.

> [!TIP]
> Seu registro de risco pode ser documentado como o exemplo abaixo:
> 
> |Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
> |---------|---------|---------|---------|---------|
> |A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas mescladas, crie um OKR separado que se aplique às suas próprias fases de projeto (Envision, Onboard, Drive Value)</li><li>Não inclua essas OKRs em OKRs existentes</li></ul>|
> |A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte à portação de número de telefone com antecedência (registro de atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</li><li>Ajustar a linha do tempo do projeto para acomodar a hora de retorno da execução de portação de número de telefone</li><li>Comunicar o uso de novos números de conferência de discagem para os participantes externos</li><li>Usar números de telefone temporários com manipulação de ID do Chamador</li></ul>|
> |Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar Teams como uma plataforma moderna de comunicação e colaboração, conduza uma avaliação de preparação de rede para sites no escopo do projeto</li></ul>|
> |Configuração SBC|Alto|Alto|Alto|<ul><li>Antes de implementar Teams como substituição para o PBX existente, confirme se você pode atender a todos os requisitos de configuração SBC</li><li>Confirme se os recursos de suporte SBC têm a habilidade adequada definida para configurar o SBC para Roteamento Direto</li></ul>|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>O que sua organização&#39;OKRs e KSIs?</li><li>Quais riscos você identificou relevantes para a implementação da Audioconferência em sua organização? Quais são os planos de mitigação para os riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação de Planos de Chamada em sua organização? Quais são os planos de mitigação para os riscos identificados?</li><li>Quais riscos você identificou relevantes para a implementação do Roteamento Direto em sua organização? Quais são os planos de mitigação para os riscos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente os OKRs e KSIs e estabeleça o registro de riscos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Estabelecer um comitê de direção

Um comitê de direção é um grupo de participantes-chave e líderes de projeto que foram unidos para orientar um projeto ou programa para seus resultados comerciais definidos. O comitê de direção não é responsável diretamente *pela* forma como o projeto é entregue, mas pelo que o projeto entrega para a empresa. 

Cada projeto requer uma visão e uma carta de acordo. Para entregar os resultados que você deseja do projeto, a visão deve ser claramente definida e precisa ser monitorada e mantida. Isso se torna responsabilidade do comitê de direção: conduzir decisões, aconselhar, fornecer supervisão estratégica, para servir como defensores da organização para as iniciativas do projeto e, quando necessário, remover bloqueadores.

Sua organização deve colocar um pensamento significativo na formação do comitê de direção. O comitê deve garantir que o projeto alcance os objetivos de negócios que você definiu para impulsionar as alterações em toda a organização, reunir-se periodicamente para discutir o pulso atual do projeto e ajudar a desbloquear todos os obstáculos que são encontrados ao longo do caminho.

O comitê deve definir sua carta para incluir alguns objetivos principais:

-   Mantenha um alinhamento forte entre a equipe de projeto e o patrocinador executivo ou a liderança executiva.

-   Forneça informações sobre o status do projeto para o patrocinador executivo ou a liderança executiva.

-   Permita que o patrocinador executivo ou a equipe de liderança executiva forneçam direção e entrada ao projeto e certifique-se de que ele se alinha com metas comerciais abrangentes, ajustando planos de projeto, resultados de chave objetiva (OKRs) e outras atividades do projeto.

O comitê de direção se reúne em um intervalo recorrente durante todo o tempo de vida de um projeto para garantir o alinhamento entre a liderança organizacional e a equipe do projeto. Essa reunião crítica garante que a direção do projeto tenha suporte total da liderança e incorpore todos os comentários fornecidos pela liderança no projeto para impulsionar o sucesso. O comitê usa essas reuniões para obter informações sobre o status do projeto e para:

-   Concorde com os resultados de negócios que se alinham ao caso de negócios e para garantir que o projeto esteja impulsionando para a entrega desses resultados.

-   Verifique e aprove o projeto para precisão e conformidade com o caso de negócios.

-   Revise e verifique as alterações feitas no caso de negócios que podem afetar quaisquer resultados definidos.

-   Tomar decisões estratégicas sobre a priorização de produtos do projeto e aprovar entregas provisórias.

-   Identifique, gerencie e reduza lacunas, riscos e problemas em que a influência adicional é necessária do comitê.

-   Reúna suporte do patrocinador executivo ou da equipe de liderança executiva para problemas que exigem escalonamento, priorização e resolução de conflitos entre unidades de negócios de partes interessadas. 

-   Forneça comentários formais e recomendações para a liderança executiva, o conselho consultivo de alterações ou outros participantes comerciais e de IT, conforme aplicável.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Pontos de decisão|<ul><li>Decida se um comitê de direção é necessário para sua organização.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Próximas etapas|<ul><li>Identificar membros do comitê de direção.</li><li>Agendar reuniões do comitê de direção.</li><li>Prepare-se para reuniões do comitê de direção.</li><li>Realizar reuniões do comitê de direção.</li><li>Tome medidas com base na entrada de reunião do comitê de direção.</li></ul>|

Orientações detalhadas adicionais sobre como operar um comitê de direção adequado podem ser encontradas no guia [do comitê de direção.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
