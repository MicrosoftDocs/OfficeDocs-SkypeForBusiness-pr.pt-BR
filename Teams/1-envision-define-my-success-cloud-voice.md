---
title: Definir o sucesso em audioconferências, o sistema telefônico com planos de chamada, ou o sistema direto roteamento de telefone - Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Medir os resultados da sua conferência de áudio, o sistema telefônico com planos de chamar ou implantação de roteamento direto de sistema do telefone e verifique se que você tiver obtido os resultados que você queria.
MS.collection: Strat_MT_TeamsAdmin
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: 334e27626a5b842bce290696052352b055767053
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866591"
---
# <a name="define-my-success"></a>Definir meu sucesso

Este artigo fornece uma visão geral dos requisitos para definir o êxito da implantação de conferência de áudio, o sistema telefônico com planos de chamar ou roteamento de telefone sistema direto para a sua organização. Ao definir corretamente o que é sucesso, você pode medir o seus resultados progressos por meio de sua implantação e verifique se a você obter os resultados são os que você queria.

<!--ENDOFSECTION-->

**Conferência de áudio** fornece organizações com pontos de entrada adicionais para as reuniões (ad-hoc ou agendadas), permitindo que os participantes ingressem via rede telefônica pública comutada (PSTN) usando a linha fixa tradicional, privados da reunião Central de comutação telefônica (PBX) ou telefones celulares. Isso é útil quando o organizador ou os participantes não estiverem na frente de um computador ou quando as conexões de dados estão indisponíveis ou muito confiável para oferecer suporte a comunicações de voz — como em uma área remota com a cobertura de dados móveis irregular, ou conectado a um Wi-Fi gratuito, público serviço com largura de banda limitada, ou quando os participantes da reunião preferem discar para a reunião usando um ponto de extremidade de telefonia que esteja prontamente acessível a eles.

**O sistema telefônico com chamar planos ("chamar planos")** dá às organizações uma maneira para modernizar o seu local de trabalho, permitindo que os usuários façam chamadas de telefone relacionado aos negócios de seus computadores e dispositivos móveis. Modernização do local de trabalho pode fazer parte de qualquer número de cenários — uma implementação do trabalho com base em atividade, mover um escritório principal, uma atualização de ajuste-out do office, retirada de uma solução de PBX herdada, a conclusão de um contrato de provedor de serviço PSTN e assim por diante. Com a chamada estiver planejando, Microsoft facilita a conectividade à PSTN.

**Sistema direto roteamento de telefone ("direto roteamento")** oferece organizações os mesmos benefícios listados acima para chamar planos, exceto pelo fato de conectividade PSTN é facilitada por um provedor de terceiros em vez de Microsoft. Isso permite para implantação nos países onde planos de chamada não estão disponíveis ou em implantações onde um contrato de provedor de serviço PSTN existente que precisam ser mantidas ou interoperabilidade com sistemas determinados local é necessária. Um cenário adicional a serem considerados direto de roteamento é interoperabilidade do sistema de telefonia. Enquanto os usuários estão sendo movidos para chamar em equipes, alguns usuários talvez permanecem no PBXs herdados. Direto roteamento permite que ambos os casos de uso para coexistir. O tráfego de chamadas entre os usuários nos sistemas herdados e equipes ficar dentro da organização.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definir os casos de uso de negócios para conferência de áudio, planos de chamar ou roteamento direto

Em primeiro lugar, participantes do projeto de núcleo precisará definir casos de uso de negócios que oferecem suporte a implementação da conferência de áudio, planos de chamar ou roteamento direto.

Casos de uso de negócios servem para definir e documentar os resultados de negócio mensurável e esperada e incluem o seguinte:

-   Descrição do processo de negócios atual

-   Desafios com o processo de negócios existentes

-   Como a tecnologia pode ajudar a superar esses desafios

-   Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.

> [!TIP]
> Este é um exemplo de um caso de uso de negócios concluídas para conferência de áudio:
>|         |
>|---------|
>|**Descrição do processo comercial atual**<br>A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.|
>|**Desafios com os processos comerciais existentes**<br>A Contoso gasta quase USD1 milhão por ano para a conferência PSTN atual de serviço, com 75% do custo que incidem sobre reuniões internas. O uso de pontos de extremidade de telefonia tradicional para participar de reuniões hospedadas pelo serviço de conferência PSTN não é alinhado com o plano para a organização adotar equipes como uma plataforma de colaboração e o communications moderno.|
>|**Como a tecnologia pode superar esses desafios**<br>Com a adoção da Microsoft Teams como uma plataforma de colaboração e o communications moderno, espera-se os usuários internos principalmente ingressar em reuniões usando seus PCs equipados com dispositivos de sala de reunião e headsets otimizadas. O serviço de conferência de áudio estarão disponível para dar suporte aos participantes externos ou para oferecer suporte a situações em que o uso de áudio para PC não é favorável para os participantes internos.|
>|**Resultados comerciais esperados e mensuráveis**<br>A mudança para equipes como um communications modernos e a plataforma de colaboração, combinado com o serviço de conferência de áudio, reduzirá bastante o custo para oferecer o serviço de conferência PSTN.|

<br>

> [!TIP]
> Este é um exemplo de um caso de uso de negócios concluídas para planos de chamada:
>|         |
>|---------|
>|**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do escritório da Contoso inclui um telefone em cada mesa. Cada funcionário recebeu uma direct inward discando o número de telefone (DID). Os telefones de área de trabalho são conectados a um sistema PBX e conectados à PSTN por meio de um tronco de (SIP) do protocolo de iniciação de sessão. Os funcionários podem fazer e receber chamadas telefônicas somente nos telefones de mesa atribuídos a eles.|
>|**Desafios com os processos comerciais existentes**<br>Análise de uso dos telefones de área de trabalho mostra que somente 10% dos telefones de mesa ativamente usados, com o restante configurado tanto para encaminhar chamadas para telefones celulares ou para ligar simultaneamente para telefones celulares. Manter o sistema PBX existente e telefones de mesa associados contribui para 20% de custo de serviço de telefonia mensal da Contoso.|
>|**Como a tecnologia pode superar esses desafios**<br>Chamar planos permitirá que o computador do pessoal de um usuário para receber e fazer chamadas telefônicas através da rede de dados utilizando o aplicativo Microsoft Teams nativo. Isso remove a necessidade de distribuir e manter os telefones de mesa e abre a oportunidade para encerrar o sistema PBX, porque o serviço de telefone pode ser entregues por meio da nuvem pela rede com nenhuma dependência de um sistema telefônico tradicional.|
>|**Resultados comerciais esperados e mensuráveis**<br>Removendo os requisitos de manutenção e o descomissionamento de PBX herdado e telefones de mesa fornecerá uma redução de 20% em telefonia mensal despesas de serviço. Chamar planos simplificará espaços de trabalho do office, permitindo que a Contoso expandir suas operações, estabelecendo novos escritórios com custos com um mínimo de telefonia antecipado.|

<br>

> [!TIP]
> Este é um exemplo de um caso de uso de negócios concluídas para roteamento direto:
>|         |
>|---------|
>|**Descrição do processo comercial atual**<br>A configuração padrão dos espaços de trabalho do escritório da Contoso inclui um telefone em cada mesa. Cada funcionário recebeu uma direct inward discando o número de telefone (DID). Os telefones de área de trabalho são conectados a um sistema PBX e conectados à PSTN por meio de um tronco de (SIP) do protocolo de iniciação de sessão. Os funcionários podem fazer e receber chamadas telefônicas somente nos telefones de mesa atribuídos a eles.|
>|**Desafios com os processos comerciais existentes**<br>Análise de uso dos telefones de área de trabalho mostra que somente 10% dos telefones de mesa ativamente usados, com o restante configurado tanto para encaminhar chamadas para telefones celulares ou para ligar simultaneamente para telefones celulares. Manter o sistema PBX existente e telefones de mesa associados contribui para 20% de custo de serviço de telefonia mensal da Contoso.|
>|**Como a tecnologia pode superar esses desafios**<br>O contrato de provedor de tronco SIP recentemente foi assinado e será in-loco por três anos. Roteamento direto permite a conectividade PSTN a ser fornecido pelo provedor de tronco SIP e também permitirá que o computador do pessoal de um usuário para receber e fazer chamadas telefônicas através da rede de dados utilizando o aplicativo Microsoft Teams nativo. Isso remove a necessidade de distribuir e manter os telefones de mesa e abre a oportunidade para encerrar o sistema PBX existente, enquanto preservam a pegada de controlador (SBC) um local limitado sessão borda.|
>|**Resultados comerciais esperados e mensuráveis**<br>Removendo os requisitos de manutenção e o descomissionamento de PBX herdado e telefones de mesa fornecerá uma redução de 20% em telefonia mensal despesas de serviço. Roteamento direto simplificará espaços de trabalho do office, permitindo que a Contoso expandir suas operações, estabelecendo novos escritórios com custos com um mínimo de telefonia antecipado.|

Além de definir seu negócio use casos, para definir os limites do projeto que deve ser visam esclarecimento unidade sobre:

-   **Escopo organizacional:** A implementação da conferência de áudio, planos de chamar ou roteamento direto pode abranger a organização inteira ou unidades de negócios específicos apenas.

-   **Cronograma do projeto:** A linha de tempo específica do projeto será executado.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Cite todos os casos de uso de negócios para conferência de áudio, você pode identificar em sua organização.</li><li>Cite todos os casos de uso de negócios para chamar planos se pode identificar em sua organização.</li><li>Cite todos os casos de uso de negócios para roteamento direta se pode identificar em sua organização.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente todos os casos de uso de negócios para audioconferências para sua organização.</li><li>Documente todos os casos de uso de negócios para chamar planos para sua organização.</li><li>Documente todos os casos de uso de negócios para roteamento direto para a sua organização.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificar as principais partes envolvidas

Os casos de uso de negócios definidos na etapa anterior incluam um escopo organizacional para a implementação da conferência de áudio, planos de chamar ou roteamento direto. Com base nisso, você pode concluir a matriz das partes interessadas abrangente para incluir as pessoas certas envolver no projeto.

> [!TIP]
> Segue um exemplo de matriz de partes envolvidas que você pode usar para documentar as partes envolvidas do projeto:
>|Função  |Descrição  |Nome, informações de contato, localização  |
>|---------|---------|---------|
>|Patrocinador executivo do projeto|<ul><li>Assumir ultimate autoridade e responsabilidade para o projeto e a entrega objetivos do projeto.</li><li>Ajuda a resolver problemas escalonados pelo líder da equipe do projeto.</li><li>Patrocinar comunicação dentro da empresa sobre os objetivos do projeto.</li><li>Verifique as principais decisões estratégicas.</li><li>Assegurar a disponibilidade de recursos necessários e o orçamento.</li><li>Levar trimestral análises dos negócios (QBRs).</li><li>Compre e apoio dos esforços da campanha de divulgação da unidade.</li><li>Servir como o patrocinador do projeto para a distribuição de programa.</li></ul>|TBA|
>|Líder de projeto|<ul><li>Gerenciar e levam a equipe de projeto.</li><li>Coordene parceiros e equipes de trabalho envolvidas no projeto.</li><li>Ser responsáveis pela criação e planos de gerenciamento de projeto atender aos resultados principais trimestrais.</li><li>Resolva problemas interfuncionais.</li><li>Fornecer atualizações regulares para responsáveis pelo projeto.</li><li>Incorpore aspectos de adoção ao plano de todo o projeto.</li><li>Liderança mensal de negócios e avaliações operacionais (MBRs), contribuir para QBRs.</li></ul>|TBA|
>|Líder/arquiteto de colaboração|<ul><li>Execute a estratégia de colaboração definida por executivos da empresa.</li><li>Analisar e escolha produtos de colaboração que atendam aos objetivos comerciais para a empresa.</li><li>Operações para produtos de colaboração de design.</li><li>Definir operação e suporte a modelos.</li><li>Contribui para análises de negócios mensais e trimestrais.</li></ul>|TBA|
>|Consultor|<ul><li>Ser responsável pelos serviços de configuração</li><li>Contribui para a arquitetura de solução geral.</li></ul>|TBA|
>|Gerente de projetos|<ul><li>Desenvolver e manter o plano de projeto.</li><li>Gerencie entregas do projeto alinhado com o plano de projeto e o orçamento.</li><li>Gravar e gerenciar problemas do projeto, incluindo escalações.</li><li>Realize chamadas standup semanais.</li><li>Faça a conexão com e fornecer, aos executivos responsáveis pelo projeto atualizações.</li><li>Trabalhar com o arquiteto para definir os planos de comunicação e a abordagem de gerenciamento alteração.</li></ul>|TBA|
>|Especialista em adoção/gerenciamento de mudanças|<ul><li>Fornecer entrada durante a fase de descoberta em processos de treinamento e adoção.</li><li>Participe do workshop de estratégia de adoção.</li><li>Desenvolver e assumir a responsabilidade para a estratégia de adoção.</li><li>Desenvolver e executar o plano de comunicação.</li><li>Entrega treinamentos aos usuários.</li><li>Coletar comentários e conduzir pesquisas.</li></ul>|TBA|
>|Líder de rede|<ul><li>Fornecer entrada durante a fase de descoberta em design de rede.</li><li>Participe de planejamento durante o workshop de fase Envision.</li><li>Coordene o trabalho da equipe de rede durante a execução do projeto.</li></ul>|TBA|
>|Líder de segurança|<ul><li>Fornecer entrada durante a fase de descoberta em processos e o design de segurança.</li><li>Participe de planejamento durante o workshop de fase Envision.</li><li>Coordene o trabalho da equipe de segurança durante a execução do projeto.</li></ul>|TBA|
>|Líder de telefonia|<ul><li>Fornecer entrada durante a fase de descoberta em design de telefonia.</li><li>Participe de planejamento durante o workshop de fase Envision.</li><li>Coordene o trabalho da equipe de telefonia durante a execução do projeto.</li></ul>|TBA|
>|Líder de desktop|<ul><li>Fornecer uma entrada durante a fase de descoberta para os clientes e o processo de atualização.</li><li>Participe de planejamento durante o workshop Envision.</li><li>Coordene o trabalho da equipe de área de trabalho durante a execução do projeto.</li></ul>|TBA|
>|Líder de suporte/suporte técnico|<ul><li>Fornecer uma entrada durante a fase de descoberta em operacionais e os modelos de suporte.</li><li>Participe de planejamento durante o workshop de fase Envision.</li><li>Participe de planejamento do suporte ao modelo.</li><li>Coordene o trabalho de equipes de suporte e recursos durante a execução do projeto.</li></ul>|TBA|
>|Representantes das unidades de negócios|<ul><li>Contribuir para guias de adoção baseada no usuário e materiais.</li><li>Contribuir para e revise os casos de uso de negócios.</li></ul>|TBA|
>|Líder de implantação|<ul><li>Certifique-se de que os pré-requisitos de implantação sejam atendidos.</li><li>Envolva os recursos a serem envolvidos nas atividades de fase Onboard.</li><li>Participe de reuniões para examinar e preparar relatórios sobre o status de implantação.</li></ul>|TBA|
>|Administradores de TI|<ul><li>Assistência com o planejamento de teste e execução. Essa função é para profissionais de TI.</li></ul>|TBA|
>|Proprietário do serviço|<ul><li>Se responsável pela operação de conferência de áudio, planos de chamar ou serviço Roteamento direto, sempre para cima.</li><li>Possui o serviço de conferência de áudio, planos de chamar ou roteamento direto.</li></ul>|TBA|
>|Defensores da qualidade|<ul><li>Unidade de comentários de qualidade, confiabilidade e usuário.</li><li>Identificar as tendências de qualidade e remediação com as respectivas equipes de unidade.</li><li>Relatar por meio do Comitê de orientação de volta à liderança.</li><li>Gerar relatórios sobre qualidade, confiabilidade e usuário sentimento por meio de taxa de chamada Meu e pontuação de Promotores Net.</li></ul>|TBA|

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Quem irá preencher cada função principal interessado para sua organização?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente todas as principais partes interessadas e comunicar as expectativas da função e responsabilidades para cada indivíduo atribuído.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definir OKRs, KSIs e riscos

Com os participantes do projeto montados, você pode converter casos de uso de negócios, escopo organizacional e cronogramas de projeto em objetivos e resultados principais (OKRs) e as medidas de sucesso do projeto podem ser definidas como uma lista de indicadores-chave para o sucesso (KSIs).

Participação completa dos participantes do projeto na definição OKRs e KSIs é essencial para ajudar a garantir que eles sentem de propriedade e alinhar dessas medidas de sucesso com os requisitos de negócios organizacionais.

OKRs contêm os objetivos que você definir no início do projeto, e você definir resultados principais mensuráveis em uma base trimestral. Você revisar resultados principais mensalmente para rastrear o status do projeto geral, e — com base em andamento — você ajustar planos trimestrais conforme necessário.

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de conferência de áudio podem ser referenciados abaixo:
><br>
>
>**Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
>|Objetivos  |Principais resultados  |Fazer  |
>|---------|---------|---------|
>|Implantar Audioconferência no Teams até o final do ano fiscal de 2018|1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
>|Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018|2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação chamando planos podem ser referenciados abaixo:
><br>
>
>**Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
>|Objetivos  |Principais resultados  |Fazer  |
>|---------|---------|---------|
>|Implantar chamar planos nas filiais European pelo final do ano fiscal 2018|FY18Q3: Implantar o chamar planos no escritório Londres|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
>|Encerrar o PBX herdado no escritório de Londres até o final do ano fiscal de 2018|4º trimestre do ano fiscal de 2018: Encerrar o PBX herdado no escritório de Londres|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

> [!TIP]
> Exemplos de OKRs relevantes para uma implementação de roteamento direto podem ser referenciados abaixo:
><br>
>
>**Visão**: Aumentar a produtividade maximizando os investimentos no Office 365
>|Objetivos  |Principais resultados  |Fazer  |
>|---------|---------|---------|
>|Implantar o roteamento direto nas filiais canadense pelo final do ano fiscal 2018|FY18Q3: Implantar o roteamento direto no office Toronto|Concepção<ul><li>Criar plano de sucesso</li><li>Criar plano detalhado de implementação técnica</li></ul><p>Integração<ul><li>Executar plano de sucesso</li><li>Executar plano de implementação técnica</li></ul>|
>|Encerre o PBX herdado no office Toronto pelo final do ano fiscal 2018|FY18Q4: Encerrar o PBX herdado no office Toronto|Gerar valor<ul><li>Aumentar o envolvimento do usuário e direcionar adoção</li><li>Gerenciar e preparar a mudança</li><li>Mensurar, compartilhar o sucesso e iterar</li>|

<br>

KSIs medir a qualidade e o êxito dos principais resultados e complementar a natureza binária do OKRs (conseguiu ou não atingidos) por detalhando resultados boas e/ou inválidos.

Ao definir KSIs, recomendamos que você use "específicos, mensuráveis, pode ser atribuídos, realistas, relacionadas ao tempo" critérios (inteligentes):

-   Específico: uma área específica, para melhoria de destino

-   Quantificam mensurável: ou sugerir pelo menos um indicador, do progresso da

-   Pode ser atribuído: especificar quem fará

-   Realista: estado o que os resultados na realidade podem ser atingido, determinados recursos disponíveis

-   Relacionadas ao tempo: especificar quando os resultados podem ser obtidos

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
>|Financeiro|Redução dos minutos de conferência herdados|Sistema financeiro|Atingir o ROI estabelecido|Baseado no ROI|Equipe de gerenciamento de mudanças|

Você precisa identificar os riscos de negócios como parte deste exercício e definir um plano de atenuação para cada risco identificado. Essas informações podem ser capturadas em um registro de riscos.

> [!TIP]
> Seu registrador de risco pode ser documentado como o exemplo a seguir:
>|Risco  |Probabilidade  |Impacto  |Geral  |Plano de mitigação  |
>|---------|---------|---------|---------|---------|
>|A incorporação acrescentará até 1.000 pessoas|Alto|Alto|Alto|<ul><li>Para empresas mescladas, crie um OKR separado que se aplica às suas próprias fases do projeto (Envision, Onboard, o valor de unidade)</li><li>Não incluir esses OKRs em OKRs existentes</li></ul>|
>|A portabilidade dos números de telefone atrasará a conclusão do projeto|Alto|Alto|Alto|<ul><li>Preparar todas as informações necessárias para dar suporte ao número de telefone portando antes do tempo (registro de serviço do cliente, detalhes da carta de autorização de cobrança)</li><li>Ajustar a cronograma do projeto para acomodar o tempo de execução de portabilidade número de telefone</li><li>Comunicar o uso de novos números de conferência de discagem para os participantes externos</li><li>Usar números de telefone temporários com a manipulação de IDs de Chamadas</li></ul>|
>|Reestruturação planejada da rede|Alto|Médio|Médio|<ul><li>Antes de implementar as equipes como uma plataforma de colaboração e o communications moderno, conduzir uma avaliação de prontidão de rede para sites no escopo do projeto</li></ul>|
>|Configuração de SBC|Alto|Alto|Alto|<ul><li>Antes de implementar as equipes como substituição para o PBX existente, confirme que você pode atender a todos os requisitos de configuração de SBC</li><li>Confirme se os recursos de suporte SBC tem o conjunto para definir o SBC para roteamento direto de habilidades adequadas</li></ul>|

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Cite OKRs e KSIs de sua organização.</li><li>Quais riscos com que você identificou relevantes à implementação da conferência de áudio em sua organização? Quais são os planos de atenuação para os riscos identificados?</li><li>Quais riscos com que você identificou relevantes para a implementação de planos de chamada em sua organização? Quais são os planos de atenuação para os riscos identificados?</li><li>Quais riscos com que você identificou relevantes para a implementação de roteamento direto na sua organização? Quais são os planos de atenuação para os riscos identificados?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente o OKRs e KSIs e estabelecer a registrar riscos.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Estabelecer um comitê de direcionamento

Comitê de direcionamento de um é um grupo de administração dos principais participantes e os líderes de projetos que tenham sido colocados juntos para orientar a um projeto ou um programa em direção seus resultados de negócios definidas. Comitê de orientação de não está diretamente responsável por *como* o projeto é entregue, mas em vez disso, *que* o projeto oferece aos negócios.

Cada projeto requer um concordou em visão e o compromisso. Para oferecer os resultados desejados no projeto, a visão deve ser claramente definida e ela precisa ser monitorados e mantido. Isso se torna a responsabilidade da comissão de direcionamento: unidade decisões, aviso, fornecer supervisão estratégico, para servir como defensores para a organização para iniciativas do projeto, e — quando necessário — remover bloqueadores.

Sua organização deve colocar pensamento significativo para a formação da comissão de direcionamento. O comitê deve assegurar que o projeto atinge os objetivos de negócios que você definiu para chegar a alteração em toda a organização, reunir periodicamente para discutir o pulso atual do projeto e ajuda a qualquer obstáculos encontradas ao longo de desbloqueio do maneira.

Comissão de deve definir seu papel para incluir alguns objetivos principais:

-   Mantenha um alinhamento forte entre a equipe de projeto e o patrocinador executivo ou liderança executiva.

-   Fornecer informações sobre o status do projeto ao Patrocinador executivo ou liderança executiva.

-   Permitir que o patrocinador executivo ou a equipe de liderança executiva fornecer a direção de entrada para o projeto e certifique-se de que ele se alinha com abrangente objetivos comerciais, ajustando planos de projeto, os resultados de chave agregados (OKRs) e outras atividades de projeto.

Comitê de orientação de atende em um intervalo recorrente durante o tempo de vida de um projeto para garantir o alinhamento entre a liderança organizacional e a equipe de projeto. Esta reunião crítico garante que a direção do projeto tem suporte completo do liderança e incorpora quaisquer comentários fornecidos pela liderança no projeto para o sucesso da unidade. Comissão de usa essas reuniões conheçam no status do projeto e para:

-   Concorda em resultados de negócios que se alinham para o caso de negócios e para garantir que o projeto está impulsionando direção a entrega desses resultados.

-   Verifique e aprovar o projeto para precisão e conformidade com o caso de negócios.

-   Revise e verifique se as alterações feitas no caso de negócios que poderia afetar quaisquer resultados definidos.

-   Tomar decisões estratégicas relacionadas a priorização de resultados finais do projeto e aprovar entregas provisórias.

-   Identificar, gerenciar e atenuar lacunas, riscos e problemas onde influência adicional é necessária do comitê.

-   Obter suporte ao Patrocinador executivo ou à equipe de liderança executiva para problemas que exigem escalonamento, priorização e resolvendo conflitos entre unidades de negócios das partes interessadas. 

-   Fornecer comentários formal e recomendações para liderança executiva, conselho, ou outras empresas e acionistas IT, conforme aplicável.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se um comitê de orientação é necessário para sua organização.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Identifica membros da comissão de direcionamento.</li><li>Agende reuniões comitê de orientação.</li><li>Prepare para reuniões comitê de orientação.</li><li>Mantenha comitê de direcionamento de reuniões.</li><li>Execute a ação com base no comitê de direcionamento de entrada da reunião.</li></ul>|

Adicional orientação detalhada sobre como operar um comitê de orientação adequado pode ser encontrada no [guia de comitê de orientação](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->