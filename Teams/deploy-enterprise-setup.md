---
title: Configure o Microsoft Teams na sua empresa
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Configure o Teams na sua empresa para permitir que seus usuários colaborem usando o bate-papo e o compartilhamento de arquivos, configurar e participar de pequenas e grandes reuniões, e conversar via vídeo e voz.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f350e894148ef278a10e379d8a32b48202acd85d
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045990"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>Configure o Microsoft Teams na sua empresa

Use as informações contidas neste artigo para orientá-lo durante a implantação do Teams na sua organização.

> [!NOTE]
> Se você ainda não fez isso, é altamente recomendável iniciar a implantação do Teams com um piloto. Um piloto permitirá que você e alguns usuários pioneiros se familiarizem com o Teams e seus recursos antes de planejar e implementar eventualmente. Para obter mais informações sobre como iniciar seu piloto, confira [Introdução ao Microsoft Teams](get-started-with-teams-quick-start.md).

Antes de lançar o Teams de forma abrangente, certifique-se de que sua organização está pronta, revendo os itens em [Certifique-se de que você está pronto](get-started-with-teams-quick-start.md#make-sure-youre-ready).

## <a name="plan-your-deployment"></a>Planeje sua implantação

Antes de começar a implantar o Teams, verifique se você concluiu o processo de planejamento. Seu processo de planejamento deve incluir:

- Compreender a arquitetura do Teams
- Revise e compreenda as cargas de trabalho do Teams e como eles funcionam com o Microsoft 365
- Requisitos de rede calculados e assegurando que sua rede e conexão à Internet tenham o hardware e a capacidade necessários para suportar requisitos críticos como comunicações em tempo real
- Compreender os requisitos regulamentares e de conformidade das informações armazenadas no Teams e em outros serviços do Microsoft 365
- Criar um plano de adoção para ajudar os usuários a entenderem os benefícios do uso do Teams

É altamente recomendável usar o consultor do [Teams](https://admin.teams.microsoft.com/teams-deployment) para ajudá-lo com sua implantação. Para obter mais detalhes sobre o funcionamento do Consultor do Teams, consulte [Use o Consultor do Teams para ajudá-lo a implantar o Microsoft Teams](use-advisor-teams-roll-out.md).

> [!TIP]
> Veja como você pode usar o Consultor do Teams para ajudá-lo a planejar sua implantação do Teams preenchendo [Implementação usando o módulo do Consultor do Teams](/learn/modules/m365-teams-rollout-using-advisor/) no Microsoft Learn.

Para obter mais informações sobre como planejar o Teams, consulte [Visão geral da implantação corporativa do Teams](deploy-enterprise-overview.md).

## <a name="workloads"></a>Cargas de trabalho

Há várias maneiras de personalizar o Teams. As seções a seguir mostram como configurar cada carga de trabalho do Teams: **chats, equipes e canais**; **reuniões e conferências**; e **Sistema de telefonia**. A ordem em que você configura cada carga de trabalho é com você. Embora seja recomendável configurar os chats, equipes e canais de carga de trabalho em primeiro lugar, você pode começar com reuniões, conferências ou até mesmo o Sistema de telefonia.

#### <a name="chat-teams-and-channels"></a>[Chat, equipes e canais](#tab/ChatTeamsChannels)

Chat, equipes e canais são a base do Teams. O **Chat** permite que um ou mais usuários conversem uns com os outros, compartilhem arquivos e se reúnam em privado. O **Teams**, que pode ser visível para todos na sua organização ou apenas para os membros da equipe, deixa as pessoas certas colaborarem em qualquer tarefa ou ocasião, seja um projeto a longo prazo ou planejar uma festa de aniversário. Os **Canais** dentro das equipes podem segmentar tópicos, projetos, departamentos ou qualquer outra coisa que faça sentido para a sua equipe. Para obter mais detalhes sobre chat, equipes e canais, consulte [Visão geral de equipes e canais](teams-channels-overview.md).

> [!TIP]
> Veja como você pode gerenciar as funções, acesso e políticas de mensagens da equipe completando o módulo [Gerenciar o Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) no Microsoft Learn.

### <a name="administration-and-team-ownership"></a>Administração e propriedade da equipe

| Decisão | Descrição |
|--|--|
| Quem devem ser os administradores do Teams? | As funções de administrador podem ser usadas para conceder permissões específicas às pessoas que você quer administrar no Teams. Talvez as pequenas empresas não precisem dessas funções extras porque a mesma pessoa pode ser responsável por todos os aspectos do Teams. Você poderá adicionar ou remover administradores posteriormente.<p>[Usar as funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md) |
| Quem devem ser proprietários e membros do Teams? | Os proprietários do Teams controlam quem pode acessar uma equipe e seus canais. Eles podem decidir se uma equipe ou canal é público (para a organização) ou privado e podem estabelecer políticas, por exemplo, se um canal deve ser moderado. Os membros podem acessar a equipe e seus canais (a menos que um canal seja privado e eles não sejam membros desse canal) e podem ser designados como moderadores.<p>[Atribuir proprietários e membros da equipe no Microsoft Teams](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>Configurações padrão e políticas de ciclo de vida

| Decisão | Descrição |
|--|--|
| Quais políticas de envio de mensagens devem ser aplicadas? | As políticas de mensagens controlam quais recursos de chat e de mensagens de canal (como quem pode usar o chat, quem pode editar e excluir mensagens enviadas, etc.) estão disponíveis para os usuários no Teams. O Teams possui uma política global que se aplica a todos. Todos os recursos da política global estão **Ativados** por padrão.<p>Se você quiser que a mesma política se aplique a todos, você só precisa fazer alterações nessa política global (por exemplo, desligar o suporte a memes nas conversas).<p>Se você quiser diferentes políticas para diferentes grupos de pessoas (por exemplo, uma política para funcionários de escritório e outra para operários de fábrica), você pode criar e atribuir políticas. Quando você atribui uma política a um usuário, a política global não se aplica mais a ele.<p>[Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md) |
| Quais configurações do Teams devem ser aplicadas? | As configurações do Teams permitem que você configure suas equipes para recursos, como integração de e-mail, opções de armazenamento em nuvem, guia de organização, configuração do dispositivo da sala de reunião e escopo da pesquisa. Quando altera essas configurações, isso se aplica a todas as equipes na sua organização. <p>[Configurações do Teams](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>Acesso externo e de convidados

| Decisão | Descrição |
|--|--|
| O acesso externo deve estar habilitado? | O acesso externo permite que qualquer pessoa em outra organização fale com as pessoas da sua organização. Isso é útil quando você possui um relacionamento próximo com outra organização, como um fornecedor, e quer facilitar a conversa entre as pessoas de ambas as organizações, realizar reuniões, e assim por diante.<p>O acesso externo é diferente do acesso de convidado. O acesso externo permite que pessoas de uma organização tenham acesso para interagirem com as pessoas de sua organização. O acesso de convidados permite o acesso de indivíduos específicos para interagirem com as pessoas da sua organização.<p>O acesso externo é **Ativado** por padrão.<p>[Gerenciar o acesso externo no Microsoft Teams](manage-external-access.md)  |
| O acesso de convidados deve estar habilitado? |O acesso de convidado permite que as pessoas da sua organização convidem pessoas de fora da sua organização para acessarem suas equipes e canais. O acesso de convidado é usado com frequência para colaborar com pessoas de fora da sua organização que não têm uma relação formal com a sua empresa. Por exemplo, você pode convidar um planejador de projeto para trabalhar temporariamente em um projeto.<p>O acesso de convidado é diferente do acesso externo. O acesso de convidado convida indivíduos específicos para interagir com pessoas em sua organização. O acesso externo permite que pessoas de outra organização tenham acesso para interagirem com as pessoas de sua organização. <p>O acesso de convidado é **Ativado** por padrão. <p>[Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team)  |

#### <a name="meetings-and-audio-conferencing"></a>[Reuniões e audioconferência](#tab/MeetingsAudioConferencing)

As reuniões e conferências permitem que as pessoas de sua organização se reúnam entre si e com pessoas de fora da organização. Qualquer pessoa com um cliente do Teams ou do Skype for Business pode participar de **reuniões** para as quais tenha sido convidada. Usar o microfone, a câmera e a tela de seu dispositivo permite que os participantes ingressem na conversa, sem a necessidade de um telefone. Os participantes podem conversar, fazer chamadas de voz e compartilhar vídeos e aplicativos com outros participantes usando um computador ou dispositivo móvel.

A **Audioconferência** permite que os participantes ingressem em reuniões por meio de um telefone comum ligando para um número de telefone em conferência e inserindo uma ID de reunião. A audioconferência é útil quando um participante não tem uma boa conexão à Internet, a reunião for apenas de voz, ou alguma outra circunstância não permitir que ele participe através do cliente do Teams.

> [!TIP]
> Familiarize-se mais com reuniões e eventos ao completar o módulo [Gerenciar reuniões, conferências e eventos com o módulo do Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) no Microsoft Learn.

### <a name="meetings"></a>Reuniões

| Decisão | Descrição |
|--|--|
| Quais configurações de reunião no mundo da organização devem ser aplicadas| As políticas de reunião controlam quais recursos de reunião estão disponíveis aos organizadores e participantes de reuniões. Você pode controlar se os participantes anônimos podem participar de reuniões, personalizar os convites das reuniões, controlar como a mídia é tratada em tempo real e muito mais. Quando você altera essas configurações, elas se aplicam a todas as reuniões da sua organização. <p>[Gerenciar configurações de reunião no Microsoft Teams](meeting-settings-in-teams.md)|
| Quais políticas de mensagens devem ser aplicadas? | As políticas de reunião são usadas para controlar os recursos disponibilizados para os participantes de reuniões programadas pelos usuários de sua organização. Você pode controlar se os usuários podem agendar reuniões privadas, habilitar a opção Reunir agora, permitir que as reuniões sejam gravadas, e assim por diante. O Teams possui uma política global que se aplica a todos.<p> Se você quiser que a mesma política se aplique a todos, você só precisa fazer alterações nessa política global (por exemplo, desligar o suporte a memes nas reuniões). <p>Se você quiser diferentes políticas para diferentes grupos de pessoas (por exemplo, uma política para funcionários de escritório e outra para executivos), você pode criar e atribuir políticas. Quando você atribui uma política a um usuário, a política global não se aplica mais a ele.<p> [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)|
| Você quer permitir a gravação e o arquivamento de reuniões?| Os organizadores da reunião podem gravar e arquivar reuniões na nuvem. Você pode ativar ou desativar a gravação e o arquivamento de reuniões usando as políticas de reunião.<p> [Gravação de reuniões na nuvem do Teams](cloud-recording.md) |

### <a name="audio-conferencing"></a>Audioconferência

| Decisão | Descrição |
|--|--|
| Você quer configurar a interoperabilidade de vídeo com as soluções de terceiros?| A interoperabilidade de vídeo em nuvem permite a telepresença de terceiros e dispositivos de vídeo pessoais para participar de reuniões do Teams. Se você já tiver investido em videoconferências e dispositivos de vídeo pessoal, pode usar a interoperabilidade de vídeo para integrar esses dispositivos ao Teams.<p> [Interoperabilidade de vídeo na nuvem para o Microsoft Teams](cloud-video-interop.md)|
| Quais configurações de reunião no mundo da organização devem ser aplicadas?| As configurações de audioconferência permitem que você controle como os participantes da reunião entram nas reuniões usando um telefone. Você pode definir a duração dos PINs necessários para participar de reuniões, redefinir IDs de conferência, habilitar ou desabilitar o envio de informações de audioconferência aos participantes, e assim por diante. As alterações nas configurações de audioconferência se aplicam a todas as pessoas da sua organização.<p>[Gerenciar as Configurações de audioconferência da sua organização no Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| Os organizadores da reunião precisam discar para qualquer destino?| Os Créditos de comunicação são usados durante as chamadas de uma reunião de audioconferência para números de telefone fora da sua organização. Você precisa ter créditos de comunicação suficientes para garantir que você não ficará sem créditos durante as chamadas de audioconferência.<p>Algumas assinaturas de audioconferência podem incluir chamadas de saída. Verifique suas informações de assinatura para obter detalhes.<p> [Configurar Créditos de comunicação da sua organização](set-up-communications-credits-for-your-organization.md)|
| Quais restrições de chamada de saída devem ser aplicadas?| Você pode usar controles de chamadas de saída para restringir o tipo de chamadas de audioconferência que podem ser feitas pelos usuários na sua organização. Por exemplo, você pode controlar se as reuniões podem realizar chamadas para números de telefone internacionais, fazer qualquer chamada de saída, ligar apenas para países ou regiões específicas, e assim por diante.<p>[Políticas de restrição de chamadas de saída de Audioconferências e Chamadas PSTN do usuário](outbound-calling-restriction-policies.md) |
| Você quer alterar a forma como os números de telefone discados são interpretados pelo Teams? | Você pode controlar como os números de telefone são interpretados usando planos de discagem. Por exemplo, você pode definir qual número discar para alcançar uma linha telefônica externa, controlar como os ramais telefônicos são tratados, definir um prefixo para que um ramal discado seja traduzido em um número de telefone completo, e assim por diante.<p> [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md) |
| Você quer habilitar eventos ao vivo? | Os eventos ao vivo permitem que você transmita vídeos e conteúdo de reuniões para grandes audiências. Se você habilitar eventos ao vivo, poderá definir políticas para que eles controlem como são usados. Por exemplo, você pode configurar a URL que os participantes devem usar como suporte, configurar um provedor de distribuição de vídeo de terceiros, se for o caso, e assim por diante. O Teams possui uma política global que se aplica a todos.<p>Se você quiser que a mesma política se aplique a todos, você só precisa fazer alterações nessa política global. <p>Se você quiser diferentes políticas para diferentes grupos de pessoas (por exemplo, uma política para funcionários de escritório e outra para executivos), você pode criar e atribuir políticas. Quando você atribui uma política a um usuário, a política global não se aplica mais a ele.<p> [Prepare-se para eventos ao vivo no Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[Sistema de telefonia e Conectividade PSTN](#tab/PhoneSystem)

O Sistema de telefonia permite que você substitua seu sistema de telefonia existente no local por um conjunto de recursos fornecidos pelo Microsoft 365 que está totalmente integrado à sua experiência na nuvem.

| Decisão | Descrição |
|--|--|
| Você quer substituir seu sistema de telefonia local? | Configure o Sistema de telefonia ao definir o atendimento automático, planos de chamadas, filas de chamadas, e assim por diante. <p> [Configurar o Sistema de telefonia da sua organização](setting-up-your-phone-system.md)|
| Você quer definir as Políticas de Caixa postal na nuvem?| Você pode controlar quais recursos de Caixa postal na nuvem estão disponíveis aos seus usuários e como eles funcionam. Por exemplo, você pode habilitar ou desabilitar a transcrição do correio de voz da sua organização, habilitar ou desabilitar o mascaramento de palavrões para usuários específicos, e assim por diante.<p> [Configurar a Caixa postal na nuvem](set-up-phone-system-voicemail.md) |
| Você quer habilitar a chamada de emergência dinâmica?| A chamada de emergência dinâmica permite que você configure um mapa de localização com base nas configurações de rede e outros metadados para determinar para onde enviar equipes de emergência no caso de uma chamada de emergência ser feita por um usuário. Você pode definir configurações de rede, atribuir endereços de emergência a locais, e assim por diante.<p>[Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md) |
| Você quer personalizar o comportamento do identificador de chamadas? | Por padrão, o número de telefone mostrado quando um usuário do Teams faz uma chamada é o número de telefone do usuário. Você pode alterá-lo para ser o número principal da empresa, bloquear o número de telefone, tornar o número anônimo, ou outro número de serviço. O Teams possui uma política global que se aplica a todos.<p>Se você quiser que a mesma política se aplique a todos, você só precisa fazer alterações nessa política global. <p>Se você quiser diferentes políticas para diferentes grupos de pessoas (por exemplo, uma política para funcionários de escritório e outra para executivos), você pode criar e atribuir políticas. Quando você atribui uma política a um usuário, a política global não se aplica mais a ele.<p> [Gerenciar políticas de identificação de chamadas no Microsoft Teams](caller-id-policies.md) |

---

## <a name="security"></a>Segurança

O Teams foi projetado e desenvolvido em conformidade com o [Ciclo de vida de desenvolvimento de segurança de computação confiável da Microsoft (SDL)](https://www.microsoft.com/sdl/default.aspx). Para estar em conformidade com o SDL, o Teams incorpora tecnologias de segurança padrão da indústria como uma parte fundamental da sua arquitetura, incluindo:

- Projetar modelos de ameaças que são testados em seguida
- Incorporação de melhorias relacionadas à segurança no processo e práticas de codificação
- Criação de ferramentas de tempo de construção para detectar sobrecargas de buffer e outras ameaças potenciais à segurança antes que o código possa ser inserido no produto

Embora as equipes sigam uma metodologia "Confiável por projeto", é impossível desenvolver projetos contra todas as ameaças à segurança desconhecidas. Por esse motivo, é importante compreender como o Teams funciona e interage com outros sistemas. Também é importante entender como as ameaças comuns, como a falsificação de endereços de IP, ataques de negação de serviço, ataques feitos por pessoas, e assim por diante, funcionam para que você possa projetar sua rede e a configuração do seu Teams para reduzir as chances desses ataques acontecerem.

Para entender como o Teams incorpora fundamentos de segurança no seu projeto e para ler mais sobre ameaças comuns, consulte [Segurança e Microsoft Teams](teams-security-guide.md).

## <a name="compliance"></a>Conformidade

O Teams e o Microsoft 365 fornecem muitas ferramentas que podem ajudá-lo a ficar em conformidade com os requisitos regulatórios onde sua empresa e seus usuários estão localizados. Consulte os seguintes artigos para obter mais informações sobre como configurar cada recurso de conformidade no Teams:

| Recurso | Descrição|
|-|-|
| [Barreiras de informações](information-barriers-in-teams.md)| Impede que indivíduos ou grupos se comuniquem uns com os outros ou que se encontrem no seletor de usuários.|
| [Políticas de retenção](retention-policies.md)| Permite que você controle o tempo de conservação dos dados no Teams ou se os dados devem ser removidos depois de certo tempo.|
| [Conformidade de comunicações](communication-compliance.md)| Ajuda a reduzir os riscos de comunicação ao identificar e adotar medidas quanto a linguagem ofensiva, profana e assediadora; imagens de conteúdo adulto e chocante; assim como o compartilhamento de informações confidenciais. |
| [Registros de chamadas e reuniões relacionados à política](teams-recording-policy.md)| Permite que você controle quando, ou se, as chamadas e reuniões devem ser registradas e armazenadas automaticamente para serem processadas, retidas ou analisadas posteriormente.|
| [Rótulos de confidencialidade](sensitivity-labels.md)| Ajuda a proteger e regular o acesso às informações confidenciais, criando rótulos que reforçam as opções de privacidade selecionadas.|
| [Prevenção Contra Perda de Dados do Microsoft Purview](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Permite criar regras que determinam como certas informações, tais como números de previdência social, números de cartão de crédito, entre outras, devem ser tratadas. Você pode proibir o envio de certas informações, impedindo que elas saiam da sua organização, e assim por diante.|
| [eDiscovery](eDiscovery-investigation.md)| Ajuda a procurar e recuperar conteúdo na sua organização, quando a mesma recebe exigências de descoberta nos processos judiciais. |
| [Retenção legal](legal-hold.md)| Ajuda a reter informações na sua organização, mesmo que sejam apagadas por um usuário, quando necessário, durante processos judiciais, para que possam ser descobertas durante investigações de eDiscovery. |
| [Pesquisa de conteúdo](content-search.md)| Fornece uma maneira de consultar as informações do Teams, que abrangem o Exchange, o SharePoint Online e o OneDrive for Business.|
| [Auditoria](audit-log-events.md)| Permite que você consulte informações a respeito de uma ação específica, incluindo quem a executou, quando ela foi executada, o endereço de IP que foi usado, e assim por diante. As ações incluem a criação ou exclusão de equipes, criação de canais, configurações alteradas no Teams e assim por diante.|
| [Chave do cliente](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Permite que você crie uma política de criptografia de dados usando chaves de criptografia fornecidas por você.|

## <a name="clients"></a>Clientes

Quando você estiver pronto para os usuários começarem a usar o Teams, eles poderão instalar o cliente do Teams em seus computadores Windows, Mac ou Linux ou em seus dispositivos Android ou iOS. Os usuários podem baixar o cliente do Teams diretamente do <https://teams.microsoft.com/downloads>.

Certifique-se de que todos que usarão o Teams tenham uma licença do Teams. Para obter mais informações de como atribuir uma licença do Teams, consulte [Gerenciar o acesso do usuário ao Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Obtenha recomendações de como planejar a implantação do cliente do Teams preenchendo o módulo [Implantar clientes do Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) no Microsoft Learn.

Se sua organização usa o Microsoft Endpoint Configuration Manager, Política de Grupo ou um mecanismo de distribuição de terceiros para implantar um software nos computadores dos seus usuários, consulte [Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager](msi-deployment.md).

Se você quiser informações detalhadas sobre como implantar os clientes do Teams, consulte [Obter clientes para o Microsoft Teams](get-clients.md).

## <a name="training"></a>Treinamento

Para obter mais informações de como treinar seus usuários e administradores para usarem o Teams, consulte [Treinamento do Microsoft Teams](training-microsoft-teams-landing-page.md).
