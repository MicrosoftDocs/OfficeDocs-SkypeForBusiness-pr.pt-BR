---
title: Preparar-se para implantar o serviço de voz na nuvem
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use listas de verificação de integração para preparar Microsoft 365 ou Office 365 para Teams e configurar Teams principais recursos, rede e cargas de trabalho de voz na nuvem.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675433"
---
# <a name="prepare-my-service"></a>Preparar meu serviço

Este artigo fornece uma visão geral dos requisitos para preparar os serviços de voz de nuvem para sua organização. Ao se preparar corretamente, você pode ter certeza de que está pronto para fornecer recursos de voz na nuvem para sua organização.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listas de verificação de integração para cargas Microsoft Teams de voz

As listas de verificação a seguir explicam as etapas para implementar o Audioconferência, o Sistema de Telefonia com planos de chamada ("Planos de Chamadas") e Sistema de Telefonia recursos de Roteamento Direto ("Roteamento Direto") no Microsoft Teams.

*  [Preparar Microsoft 365 ou Office 365 para Teams](onboarding-checklist-enable-office-365.md)

*  [Configurar Teams principais recursos](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparar sua rede](prepare-network.md)

*  [Configurar cargas de trabalho de voz na nuvem Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurar o Roteamento Direto Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

As tarefas e atividades nessas listas de verificação são os principais itens "pendentes" que se aplicam a cada implantação de recursos de voz na nuvem com Teams. Você pode personalizar as listas de verificação para incluir as atividades e tarefas específicas para seu próprio Teams de trabalho.

>[!NOTE]
>Essas diretrizes se concentram exclusivamente em Planos de Chamadas, Audioconferência e Roteamento Direto. Se você não tiver experiência com Teams, examine a [Visão geral do Microsoft Teams](teams-overview.md). Para obter diretrizes gerais para planejar sua implantação Teams, comece com Implantar [chat, equipes, canais e aplicativos no Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Use as listas de verificação fornecidas para acompanhar o status de cada atividade e tarefa individual e para ter certeza de que você não ignorou nenhuma etapa crítica. Cada atividade inclui uma descrição detalhada das ações e referências necessárias a informações adicionais que você pode usar para concluir essa atividade.

Embora seja recomendável que você siga as listas de verificação na ordem, a sequência exata dependerá do escopo da implantação e da configuração e da complexidade do seu ambiente. Eles são organizados para dar suporte a uma implantação de Teams "greenfield" (uma sem presença anterior do Skype for Business Online) ou migrando do Skype for Business Online para o Teams. Se você estiver migrando do Skype for Business Online, talvez já tenha concluído algumas dessas atividades e possa ignorá-las agora.

Quando você está integrando usuários por site, é altamente recomendável usar o Guia Estratégico de Habilitação do Site para Voz (Guia Estratégico [)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia suplementar para essas listas de verificação.

>[!NOTE]
>A maioria das definições de configuração é comum entre Teams e Skype for Business Online. Use o centro Administração Microsoft 365 e o Microsoft Teams de administração para definir essas configurações.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Who será responsável por supervisionar a conclusão das listas de verificação de integração?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Baixe as listas de verificação de integração.</li><li>Trabalhe passo a passo nos itens da lista de verificação de integração de acordo com o plano de implantação da sua organização.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuar a integração

Depois de concluir essas listas de verificação, você terá adicionado com êxito recursos de voz à sua implantação Teams serviço.

Como a próxima etapa, use o Guia Estratégico de Habilitação do Site para Voz [(Guia Estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a integrar seus usuários em cada site e ajudar a garantir que você planeje e execute atividades importantes específicas do site.

-   Plano de distribuição site a site pronto

-   Estabelecer processo de gerenciamento de serviços

-   Executar teste e correção

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testar cargas de trabalho de voz na nuvem Teams

Depois de definir e documentar seus planos de sucesso e implementação técnica do Teams Cloud Voice Business como parte da fase de Concepção e realizar a configuração desejada no centro de administração, a próxima etapa é validar se as expectativas e os requisitos da sua organização são atendidos por meio de recursos, funcionalidades e usabilidade. Você deve executar essa etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.

Você pode aproveitar o plano de sucesso empresarial definido durante a fase de Concepção para servir como base para determinar as atividades, as expectativas, os casos de teste de recursos/funcionalidades e o escopo geral a ser avaliado durante a fase de teste.

## <a name="define-your-testing-approach"></a>Definir sua abordagem de teste

Em sua forma mais simples, sua abordagem de teste baseia-se na revisão dos recursos do serviço Audioconferência, planos de chamada ou roteamento direto e no desenvolvimento de um plano de teste para verificar se os requisitos de funcionalidade são atendidos para usuários no escopo. A seguir está um plano de teste de exemplo para a fase De integração de uma implementação de audioconferência.


| Audioconferência recurso a ser testado | Resumo dos resultados | Observações adicionais |
|------------|-----------------|------------------|
| Agendar uma reunião Teams ad hoc que contenha informações de discagem de audioconferência | Pass/Fail   | TBD |
| Use um telefone para o áudio da reunião discando em uma reunião do PSTN com as informações de discagem fornecidas | Pass/Fail | TBD |
| Ingressar outras pessoas em uma reunião existente discando por meio do PSTN | Pass/Fail | TBD |



| Planos de Chamadas ou Recurso de Roteamento Direto para teste | Resumo dos resultados | Observações adicionais |
|----------------------------------------------------|-----------------|------------------|
| Fazer uma chamada PSTN discando um número PSTN       | Pass/Fail       | TBD |
| Receber uma chamada PSTN discando seu número PSTN de uma linha externa (celular, telefone fixo) | Pass/Fail | TBD|
| Transferir uma chamada PSTN de um Teams usuário para outro | Pass/Fail | TBD |


>[!TIP]
>Para ajudar na criação de casos de teste como ponto de partida, consulte a lista de diretrizes de usuário disponíveis em reuniões [Teams chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurar cargas de trabalho de voz na nuvem para Teams

Agora que você definiu sua abordagem de teste, a próxima etapa é configurar o ambiente de serviço e os usuários no escopo para Teams de voz na nuvem.

Para obter informações adicionais, consulte:

- [Planejamento técnico da Audioconferência](./cloud-voice-landing-page.md)

- [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planejamento técnico para Sistema de Telefonia com planos de chamada](calling-plan-landing-page.md)

- [Configurar Planos de Chamadas para Skype for Business e Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planejar o Roteamento Direto](./direct-routing-plan.md)

- [Configurar o Roteamento Direto](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Executar o plano de teste

[//]: # (Editar tudo bem? "Usuário" me pareceu um pouco ambíguo.)
Depois que o ambiente do usuário e o serviço tiverem sido configurados, a última etapa de teste incluirá a execução do plano de teste com foco na validação de recursos e funcionalidades. 

**Audioconferência pré-requisitos e suposições de teste para usuários e sites no escopo:**

-   Definição de caso de uso empresarial para o Audioconferência serviço foi concluído.

-   O licenciamento necessário para Audioconferência está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   A lista de discagem de audioconferência dedicada e compartilhada em números com preferência de idioma foi identificada e configurada.

-   [Os Créditos de](what-are-communications-credits.md) Comunicação (se necessário) foram configurados para sua organização.

-   Audioconferência de ponte de conferência foram identificadas e definidas (comprimento do PIN, notificações de entrada/saída, preferência de notificação de habilitação).

-   As políticas de conferência de locatário e as configurações de plano de discagem que dão suporte Audioconferência de discagem foram identificadas, configuradas e aplicadas.

-   Audioconferência requisitos de conformidade foram identificados e configurados.

**Planos de Chamadas testando pré-requisitos e suposições para usuários e sites no escopo:**

-   A definição de caso de uso empresarial para o serviço planos de chamada foi concluída.

-   O licenciamento necessário para Planos de Chamadas está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Telefone números a serem atribuídos aos usuários foram adquiridos ou portados para a Microsoft e estão disponíveis no portal do locatário.

-   [Os Créditos de](what-are-communications-credits.md) Comunicação (se necessário) foram configurados para sua organização.

-   As políticas de usuário de locatário e as configurações de plano de discagem que dão suporte a cenários de Planos de Chamadas foram identificadas, configuradas e aplicadas.

-   Os requisitos de conformidade dos Planos de Chamadas foram identificados e configurados.

**Pré-requisitos e suposições de teste de roteamento direto para usuários e sites no escopo:**

-   A definição de caso de uso empresarial para o serviço de Roteamento Direto foi concluída.

-   O licenciamento necessário para o Roteamento Direto está disponível e foi atribuído.

-   A lista de sites organizacionais e grupos de usuários foi identificada.

-   Um [SBC (controlador de borda de sessão)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) certificado foi implantado, configurado e emparelhado com Sistema de Telefonia.

-   Enterprise voz foi habilitada e os números de telefone foram atribuídos.

-   As políticas de roteamento de voz foram identificadas, configuradas e atribuídas.

-   Microsoft Teams foi definido como o cliente de chamada preferencial para os usuários no escopo.
 
-   Os requisitos de conformidade do Roteamento Direto foram identificados e configurados.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida quais Audioconferência recursos serão implantados (decisão de serviço).</li><li>Identificar os requisitos de funcionalidade do usuário para Audioconferência.</li><li>Identificar os requisitos de configuração de serviço Audioconferência.</li><br><li>Decida se o Roteamento Direto ou Os Planos de Chamadas serão implantados e configurados.<li>Decida quais Sistema de Telefonia recursos serão implantados (decisão de serviço).</li><li>Identifique os requisitos de funcionalidade do usuário para Planos de Chamadas ou Roteamento Direto.</li><li>Identificar o requisito de configuração de serviço para Planos de Chamadas ou Roteamento Direto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li>Desenvolva e documente sua abordagem de plano de teste.</li><li>Prepare o ambiente de serviço e os usuários no escopo para Audioconferência recursos.</li><li>Prepare seu ambiente de serviço e usuários no escopo para planos de chamadas ou recursos de roteamento direto.</li><li>Execute a validação de teste para Audioconferência recursos que você deseja habilitar.</li><li>Execute a validação de teste para os planos de chamada ou os recursos de Roteamento Direto que você deseja habilitar.</li><li>Para falhas de teste, confirme se a configuração está correta, examine os artigos da comunidade e, se necessário, gere um caso de suporte.</li></ul></td></tr>
</table>


Para obter diretrizes detalhadas adicionais sobre como executar testes para Audioconferência no Teams, consulte o guia de teste detalhado para [Audioconferência.](./deploy-audio-conferencing-teams-landing-page.md)

Para obter diretrizes detalhadas adicionais sobre como executar testes para Planos de Chamadas no Teams, consulte o guia de teste detalhado para [Sistema de Telefonia.](./cloud-voice-landing-page.md)

<!--ENDOFSECTION-->