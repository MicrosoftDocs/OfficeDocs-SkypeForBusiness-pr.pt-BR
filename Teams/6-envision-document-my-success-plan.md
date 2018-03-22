---
title: Documente o seu planejamento de sucesso Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Escolher um modelo de implantação, desenvolver uma matriz de (RACI) responsável-responsável-consultado-informados, criar planos a governança e execução.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8352608eca00062ed2b8dbdce4682e7bdd437351
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
# <a name="document-my-success-plan"></a>Documente o meu planejamento de sucesso

## <a name="execution-planning"></a>Planejamento de execução 

Depois de definir como você implementará a conferência de áudio ou de um sistema telefônico com a solução de planejamento de chamar em sua organização, você precisa planejar a execução do projeto de implementação.

Se sua organização tiver apenas um ou dois sites, você não precisará concluir todos os detalhes fornecidos neste artigo, mas você deve ler através dele para orientar sua abordagem.

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>Modelo de implantação 

Como com qualquer implementação de tecnologia que transforma a maneira como as pessoas trabalham em sua organização, escolhendo a maneira correta de realizar a implantação influenciará bastante o sucesso da sua implementação de voz de nuvem.

Modelos de implantação possíveis incluem o seguinte:

-   **Por site:** Este modelo é adequado para casos em que sua organização seja geograficamente dispersa e ramificações tiverem números significativos dos funcionários. No entanto, esse modelo de implantação potencialmente pode interromper a comunicação em departamentos em que os funcionários do departamento estão espalhados por vários locais.

-   **Por divisão**: este modelo normalmente é a melhor opção para empresas de médio porte e garante que os departamentos envolvidas tenham a mesma experiência.

-   **Toda a empresa ao mesmo tempo:** Este modelo é geralmente a melhor opção para empresas de pequeno, onde todos os funcionários obtém a mesma experiência desde o início da implantação.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida o modelo de execução de implantação de equipes que se aplica à sua organização.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o modelo de execução de implantação de equipes que você escolheu e inclua justificativas técnicas e negócios.</li></ul></td></tr></table>

##<a name="raci-modeling"></a>Modelagem de RACI

Para garantir que você acaba de criar clareza para quem é responsável pelo quê em seu projeto, use uma matriz de atribuição de responsabilidade (também conhecido como um RACI — responsável, responsável, consultado e informados — matriz). A pessoa ou grupo que é responsável e responsáveis por cada tarefa, juntamente com os participantes para ser consultada no processo de tomada de decisão e participantes para ficar informado sobre de cada decisão e a ação durante a execução de projeto de lista.

O exemplo a seguir é um exemplo de uma matriz de RACI para uma implementação de voz de nuvem.

| Função de atividade /                                         | Líder de projeto | Líder/arquiteto de colaboração | Consultor | Especialista em adoção/gerenciamento de mudanças | Representantes das unidades de negócios |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| Chamada de abertura de apresentação do programa                     | R, UMA         | C                            |            |                                       |                               |
| Configurar o painel de controle de qualidade de chamada                         | I            | C                            | R, UMA       |                                       |                               |
| Compartilhar o questionário de descoberta durante a chamada de abertura | I            | C                            | R, UMA       |                                       |                               |
| Prever abertura da fase                                | R, UMA         | C                            |            |                                       |                               |
| Workshop de casos de uso de negócios                           | A            |                              |            | R                                     | C                             |
| Revise o questionário de descoberta                    |              | R, UMA                         | C          |                                       |                               |
| Workshop de arquitetura                                 | I            | R, UMA                         | C          |                                       |                               |
| Workshop do adoção usuário cenários Envision fase       | C            | I                            | A          | R                                     |                               |
| Workshop de sucesso da adoção                             |              |                              | R, UMA       | C                                     |                               |
| Workshop de preparação de clientes e dispositivos                  | I            |                              | R, UMA       | C                                     |                               |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida as atividades/funções relevantes para o projeto de implementação de voz de nuvem.</li><li>Decida o equipes ou a pessoa a ser atribuído a matriz de atribuição de responsabilidade (matriz RACI) do projeto de implementação de voz de nuvem.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>A matriz RACI do documento.</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>Plano de execução trimestral

Para executar a implantação de voz de nuvem em partes gerenciáveis de trabalho, é recomendável que você crie um plano de execução trimestral com base em seus resultados principais agregados (OKRs), o modelo de implantação que você escolheu e a capacidade de execução do projeto da sua organização.

Dessa maneira, você pode controlar o andamento em uma base trimestral, revisar o plano, se necessário e implantar com base na capacidade da sua organização para executar recursos de voz de nuvem.

Se sua organização tiver apenas um ou dois sites, talvez não seja necessário um plano de execução trimestral porque você esperaria totalmente seja implantado em um curto período de tempo.

O exemplo a seguir é um exemplo de um plano de execução trimestral para a fase de Envision de uma implementação de voz de nuvem.

| Site/divisão                            | Número de funcionários | Audioconferência | Sistema de Telefonia                    | Trimestre para executar |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| Estados Unidos: Nova York                             | 2000                | Sim                | Sistema de Telefonia com Planos de Chamadas | CY2018 T1          |
| Irlanda: Dublin                          | 300                 | Sim                | Sistema de Telefonia com Planos de Chamadas | CY2018 T1          |
| Áustria: Viena                          | 500                 | Sim                | N/A                             | T2 CY2018          |
| Itália: Milão                             | 200                 | Sim                | N/A                             | T2 CY2018          |
| América do Sul: Brasil                    | 1500                | Sim                | N/A                             | T2 CY2018          |
| Índia: Délhi                             | 7000                | Sim                | N/A                             | T3 CY2018          |


<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida o plano de execução trimestral para alcançar os resultados principais agregados (OKRs).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o plano de execução trimestral.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>Comunicações e plano de governança

Para manter os participantes do projeto atualizado com o progresso da implantação, você precisa estabelecer um plano para como communications entrarão em vigor entre o núcleo membros da equipe de projeto e com os participantes para discutir assuntos relativos ao status do projeto, principais marcos, bloqueadores e várias avaliações do projeto contra KSIs estabelecidas, as métricas operacionais e objetivos estratégicos.

O exemplo a seguir é um exemplo de um plano de governança e de comunicação que você pode aproveitar em seu projeto de implementação de voz de nuvem.

| Tipo                                        | Metas                                                                                                                                                      | Participantes | Dias/hora                                     | Local             | Proprietário da reunião |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Chamadas standup do projeto                       | Sincronizar o status do projeto, rastrear bloqueadores e fatos importantes                                                                                           | TBA          | Segunda-feira, terça-feira, quarta-feira, quinta-feira, 5 PM PST | Virtual              | TBA           |
| Comitê de orientação semanal                   | Revise o status do projeto de voz de nuvem, relatado executivos, eleve que exigem executiva ajuda para resolver problemas                                        | TBA          | Toda sexta-feira 11 AM PST                        | Virtual              | TBA           |
| Revisão de negócios/operacionais project mensal | Verificar o status do projeto com participantes estendidos, principais pontos de contato e executivos responsáveis; examinar o plano de implantação, KSIs e avaliações operacionais | TBA          | Segunda terça-feira do mês                       | Virtual ou pessoalmente | TBA           |
| Revisão de negócios trimestral (QBR)             | Verificar o status do projeto e revise o progresso em relação às metas estratégicas, KSIs e avaliações operacionais; Rever planos, se necessário                                 | TBA          | Última quinta-feira de cada trimestre                | Pessoalmente            | TBA           |


<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida de comunicação e um plano de governança, incluindo a frequência de métodos de (diariamente, semanalmente, mensalmente ou trimestral), de atualizações de status regular para conduzir reuniões de atualização de status e o proprietário de cada reunião.</li></ul></td></tr>

<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Documente o plano de governança e de comunicação.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>Finalizar meu plano de sucesso

Um plano de sucesso é o resumo da documentação que você criou na fase de Envision.

O plano de sucesso dá a equipe de projeto — que podem incluir FastTrack ou um parceiro de implantação — informações suficientes para concretizar metas da sua organização com implementar a conferência de áudio ou de um sistema telefônico com serviço de plano de chamada.

Em geral, um plano de sucesso contém as seguintes seções principais, muitos que você irá tiver trabalhado por meio da fase Envision:

-   Caso de negócios

-   Prontidão de serviço

-   Decisões de serviço

-   Plano de execução

-   Plano de adoção

-   Plano operacional

### <a name="business-case"></a>Caso de negócios

Exemplos de uso de negócios, a lista de participantes, OKRs e KSIs, registradores de risco e cronogramas dos projetos geralmente compõem a maior parte das informações necessárias para um caso de negócios. Você deve documentar isso como parte do seu plano de sucesso.

### <a name="service-readiness"></a>Prontidão de serviço

Avaliação do seu ambiente fornece as informações de iniciais exigidas para determinar a prontidão técnica da sua organização para implementar a conferência de áudio e/ou o sistema telefônico com chamar planejar.

Incluídos aqui é sua avaliação de prontidão do serviço e o plano para áreas de endereço que precisam de remediação descobertos por meio da avaliação do ambiente.

### <a name="service-decisions"></a>Decisões de serviço

Documente como você planejou a conferência de áudio ou de um sistema telefônico com chamar planejar a implementação de técnicos do serviço para a sua organização.

### <a name="execution-plan"></a>Plano de execução

Como você planejou a execução do projeto para implementar a solução em toda a organização do documento.

### <a name="adoption-plan"></a>Plano de adoção

Depois de executar sua avaliação de prontidão de adoção, a equipe de projeto precisa para surgir com um conjunto abrangente de planos de comunicação, um plano de treinamento e planos de pré-lançamento, inicialização e POST-iniciar atividades de adoção.

Identificar recursos usados para oferecer suporte às atividades de adoção, como folhetos, de boas-vindas emails e material de treinamento, junto com quaisquer personalizações que você precisará para atender aos requisitos da sua organização.

Baixe modelos de adoção de atividades do [Kit de sucesso do cliente do Microsoft equipes](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plano operacional

O exercício de mapeamento de funções operacionais estabelecerá funções e responsabilidades e as equipes atribuídas a cada função operacional, o que você precisa oferecer suporte à implementação de conferência de áudio.

Você precisa inserir isso e incluir o plano operacional como parte do plano de sucesso para garantir a prontidão operacional da solução.

<table>

<tr><td>![](media/audio_conferencing_image7.png) <br/>Pontos de decisão</td><td><ul><li>Decida como você irá Documente o seu planejamento de sucesso inteira proporciona sua nuvem cargas de trabalho de voz.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Próximos passos</td><td><ul><li>Confirme se todos os componentes do seu plano de sucesso foram documentados.</li><li>Agregar componentes individuais do seu plano de sucesso em um único documento resumo (opcional).</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
