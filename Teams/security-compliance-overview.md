---
title: Visão geral de segurança e conformidade no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Uma visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, eDiscovery e muito mais.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857e4b691256ff13b6f9308bcd9fb12dfb10297d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Visão geral de segurança e conformidade no Microsoft Teams
======================================================

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam.

O Teams tem conformidade de Camada C no lançamento. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://go.microsoft.com/fwlink/?linkid=855777). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

O Teams também aplica uma autenticação de dois fatores para todas as equipe e organizações, registro único através do diretório ativo e criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote.

Também acrescentamos suporte para pesquisa de registros de auditoria, eDiscovery e retenção legal para canais, bate-papos e arquivos, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Vá para o Centro de conformidade de segurança do Office 365 para gerenciar essas configurações. 

## <a name="auditing-and-reporting"></a>Auditoria e relatórios

A pesquisa de registros de auditoria se conecta diretamente ao Centro de Segurança e Conformidade do Office 365 e tem a capacidade de configurar alertas e/ou relatórios em um evento de auditoria ao disponibilizar e exportar conjuntos de eventos de carga de trabalho genéricos ou específicos para uso e pesquisa do administrador em uma linha de tempo de auditoria ilimitada. Todos os dados de registro de auditoria estão disponíveis para configurar aletas no Centro de Segurança e Conformidade do Office 365, bem como para filtragem e exportação para análises mais profundas.

## <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

A pesquisa de conteúdo pode ser usada para fazer pesquisas no Microsoft Teams por meio de funcionalidades sofisticadas de filtragem e exportada para um contêiner específico para dar suporte à conformidade e litígios. Isso pode ser feito com ou sem um caso do eDiscovery.

## <a name="ediscovery"></a>eDiscovery

A descoberta eletrônica é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação judicial ou investigação.

Recursos incluem o gerenciamento de casos, preservação, pesquisa, análise e exportação de dados de equipes. Isso inclui bate-papos, mensagens e dados de arquivos.

Os clientes podem se beneficiar do In-place eDiscovery ou do [Advanced eDiscovery](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)

As diferenças entre os dois estão destacadas na tabela a seguir:


| |In-place eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Gestão de casos     |X        |X         |
|Controle de acesso  |X         |X         |
|Pesquisa de conteúdo     |X         | X        |
|Retenções   |X         | X        |
|Exportar     |X         |X         |
|Detecção de duplicidade     |-         |X         |
|Pesquisa de relevância com aprendizagem de máquina    |-         |X         |
|Análise de dados não estruturados      |-         |X         |


## <a name="legal-hold"></a>Retenção legal

Quando uma equipe do Microsoft Teams é colocada em Bloqueio In-loco ou em Retenção de Litígio, a retenção é colocada na caixa de correio dos grupos.

As retenções locais costumam ser aplicadas no contexto de um caso do eDiscovery.

A figura abaixo indica o fluxo de trabalho dos dados do Teams para o Exchange e o SharePoint.

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> Pode haver um atraso de até 24 horas para revelar o conteúdo do Teams.


## <a name="retention-policies"></a>Políticas de retenção

As equipes conversas são persistentes e retido para sempre por padrão. Com a introdução das políticas de retenção, admins pode configurar políticas de retenção (preservação e exclusão) no Centro de conformidade de segurança para mensagens de chat e canal de equipes. Isso ajuda as organizações a reter dados para fins de conformidade (isto é, a diretiva de preservação) por um período específico ou se livrar de dados (ou seja, a política de exclusão), se ele é considerado um passivo após um período específico. Políticas de retenção de equipes Certifique-se de que, quando você exclui dados, ele será removido de todos os locais de armazenamento de dados permanentes no serviço equipes. 

Para gerenciar políticas de retenção de equipes works usar os cmdlets e configurações no Centro de conformidade de segurança do Office 365 em **Dados governança** > **retenção**.

Políticas de retenção de equipes têm suporte para: 
    
- Preservação: Manter dados de equipes por um período especificado e, em seguida, eu não fizer nada
- Preservação e, em seguida, excluir: manter dados de equipes por um período especificado e excluir
- Exclusão: Excluir dados de equipes após um período especificado

Políticas de retenção de equipes ainda não suportam:

- Políticas de retenção avançadas não se aplicam ao chat de equipes e locais de mensagem de canal de equipes
- Duração de menos de 30 dias

Administradores podem configurar políticas de retenção separados para mensagens de canal de equipes e chats privadas de equipes (1:1 ou 1: muitos chats). Em muitos casos, as organizações considerar os dados de bate-papo privado como mais de uma obrigação de mensagens de canal, que geralmente são mais conversas relacionados ao projeto. Configurar essas diretivas na Central de segurança e conformidade, **Governança dados** > **retenção**. Ative **equipes mensagens de canal** e **equipes de bate-papos** e, em seguida, definir políticas de retenção desses locais (também é mostradas no diagrama a seguir). 

Quando você ativa **as mensagens de canal de equipes**, você pode especificar as equipes ao qual esta política será aplicada. Por exemplo, para as equipes X, Y e Z, o administrador pode definir as políticas de exclusão por 1 ano (selecionando essas equipes individualmente) e aplicar uma política de exclusão de 3 anos para o restante das equipes. 

Você pode fazer a mesma coisa por **equipes chats** selecionando usuários específicos e aplicar políticas de retenção exclusivo. 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Os locais de mensagem do canal de equipes e os locais de chats de equipes apenas endereços as conversas de equipes armazenadas em caixas de correio Exchange Online (caixas de correio grupo e usuário). As mensagens são excluídas de todos os locais de armazenamento relevantes, notadamente as caixas de correio, substrate e serviço de bate-papo. 
> 
> Para gerenciar políticas de retenção para arquivos de equipes, que são armazenados no OneDrive para negócios e do SharePoint, use suas políticas de retenção.




Por design, as políticas de exclusão para arquivos de equipes são configuradas por meio do SharePoint Online e OneDrive para locais de negócios. Como resultado, é possível que uma política foi possível excluir um arquivo referenciado em uma mensagem de bate-papo ou canal de equipes antes que essas mensagens são excluídas. Nesse caso, o arquivo ainda serão exibidas na mensagem de equipes, mas se você clicar no arquivo, você receberá um erro "Arquivo não encontrado" (Isso também pode acontecer na ausência de uma política, se alguém manualmente exclui um arquivo do SharePoint Online ou do OneDrive for Business).


Para obter informações detalhadas sobre como configurar as políticas de retenção para o Office 365, leia a [Visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Perguntas frequentes sobre as políticas de retenção

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>Quais tipos de políticas podem configurar o modo em políticas de retenção e como elas funcionam?

Na Central de segurança e conformidade, quando você configurar uma política de retenção, para equipes ou para qualquer outra carga de trabalho, você pode configurar dois tipos principais de políticas: 
- Preservação: Essas políticas garantir que seus dados seja preservados para um determinado período de tempo, não importa o que acontece nas ferramentas do usuário final. Eles garantem que dados são preservados por motivos de conformidade e expira disponíveis no eDiscovery até neste momento. Após o tempo de expiração, sua política pode indicar se deseja fazer nada ou excluir os dados. Em equipes, se você criar uma política de preservação para 7 anos, mesmo se os usuários finais excluir suas mensagens de equipes, essas mensagens são preservadas para descoberta eletrônica por 7 anos.
- Exclusão: Essas políticas garantem que os dados não são um risco para sua organização. Após o período especificado, os dados são excluídos do todo o armazenamento em equipes relevante. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Podemos incluir equipes em políticas de toda a organização? 

Não, não no momento. Você deve criar políticas específicas para mensagens de chat e canal de equipes usando a linha de local de equipes ou esses cmdlets equipes: New-TeamsRetentionCompliancePolicy & New-TeamsComplianceRetentionRule. Esses cmdlets ter get e definir as versões também.

### <a name="are-these-retention-policies-retroactive"></a>Essas políticas de retenção são retroativas? 

Sim, eles são. Se você criar uma política de retenção para excluir os dados mais antigos do que 60 dias, ele excluirá dados de equipes criados há mais de 60 dias. 

### <a name="what-is-the-default-retention-policy"></a>Qual é a política de retenção padrão? 

Por padrão, o bate-papo equipes, de canal e dados de arquivos são mantidos indefinidamente. Um usuário pode excluir alguma coisa, mas na ausência de políticas de retenção, dados de equipes sempre serão arquivados no Exchange online mailboxes. (de usuário e de grupo) em permanecem lá para descoberta eletrônica. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Conjuntos de usuários ou equipes em uma política pode direcionar? 

Sim, você deve fazer. No Assistente de criação de política, na etapa locais, pode incluir ou excluir usuários (**chat equipes**) ou equipes (**mensagens de canal de equipes**) e criar políticas de destino para a sua organização. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>O que é a principal diferença entre usando a linha do local de caixa de correio de grupo e a linha de local de mensagens de canal de equipes em políticas de retenção? 

Se você usar a caixa de correio de grupo e linhas de local de caixa de correio do usuário para o Exchange Online, equipes de dados serão excluídas das caixas de correio especificadas. No entanto, isso só remove dados da caixa de correio. Ela não exclui os outros dados de equipes, como o serviço de bate-papos. É recomendável usar políticas de retenção de equipes para gerenciar todos os dados de equipes de forma adequada. Uma política de retenção de equipes remove dados de equipes de todos os armazenamento locais – caixas de correio, serviço de Chat, os clientes de equipes. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>O que acontece com Skype para chats de interoperabilidade Business Online e equipes – eles são afetados pelas políticas de retenção?

Sim, Skype para Business Online e chats de interoperabilidade de equipes funciona da mesma maneira. Depois que o Skype para chat Business Online entra em equipes, ela se torna uma mensagem em um segmento de bate-papo de equipes e obtém incluída em uma caixa de correio apropriada. Para que o mesmo fluxo works – políticas de exclusão de equipes excluirá essas mensagens do thread equipes. No entanto, se o histórico da conversa está ativado para Skype para Business Online e do Skype para Business Online lado do cliente aqueles estão sendo salvos em uma caixa de correio, esses dados de chat não são tratados por uma política de retenção de equipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Posso fazer essas por meio de cmdlets do Centro de conformidade de segurança? O que devo usar? 

Absolutamente. Você pode criar políticas de retenção de equipes usando [cmdlets do Powershell do Centro de conformidade & segurança]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Lembre-se de que não estão cmdlets do Exchange Online. Aqui estão os cmdlets que criamos para equipes. Eles siga o estilo e a nomenclatura existente da retenção cmdlets atualmente disponíveis no Centro de conformidade de segurança.

|Política|Regra|
|---|---|
|New-TeamsRetentionCompliancePolicy| New-TeamsRetentionComplianceRule|
|Get-TeamsRetentionCompliancePolicy| Get-TeamsRetentionComplianceRule|
|Get - TeamsRetentionCompliancePolicy| Set - TeamsRetentionComplianceRule|
|Remove - TeamsRetentionCompliancePolicy| Remove - TeamsRetentionComplianceRule|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Se houver várias políticas de retenção para equipes variadas durações, qual delas wins?

Podemos seguem [princípios das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)e recomendamos que você faça muito. A resposta curta é: 
-   Preservação sempre supera exclusão
-   Maior período de preservação sempre wins
-   Inclusão explícita supera implícita inclusão em termos de locais
-   Mais curta wins período de exclusão



## <a name="retention-policies-known-issues"></a>Problemas conhecidos de políticas de retenção

1. Em Escolha equipes na linha local de mensagens do canal de equipes, talvez você veja os grupos do Office 365 que são não também às equipes. Isto será abordado no futuro.

1. Em Escolha usuários na linha local equipes de bate-papo, talvez você veja convidados e os usuários não-mailbox. Políticas de retenção não devem ser definidos para convidados e estamos trabalhando para removê-los da lista. 

1. Assistente de ciclo de vida do Exchange (ELC) executado diariamente, mas ele tem um SLA de 7 dias. Como resultado, é possível que, se você tiver uma política de retenção de equipes para excluir itens mais antigos do que 60 dias, esses itens poderiam persistem até 67 dias. Isso não é uma nova situação - vier o modelo do Exchange. Obviamente, na maioria dos casos, não há nenhum atraso.


| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |Quais são os recursos de segurança e conformidade exigidos pela sua organização? A sua organização tem as licenças necessárias para atender aos requisitos empresariais de segurança e conformidade?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Próximos passos         |Documente seus recursos de segurança e conformidade necessários.         |

<a name="licensing"></a>Licenças
---------------

Quando falamos em recursos de proteção de informações, as assinaturas do Office 365 e as licenças autônomas associadas determinarão o conjunto de recursos disponíveis.

|Recurso de proteção da informação   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|Arquivamento|-  |-   |-   |Sim   |Sim   |
|In-Place eDiscovery|-   |-   |-   |Sim   |Sim   |
|Advanced eDiscovery|-   |-   |-   |-   |Sim   |
|Retenção legal|-   |-   |-   |Sim   |Sim   |
|Pesquisa de conteúdo de conformidade|- |- |- |Sim |Sim |
|Auditoria e relatórios|Sim |Sim |Sim |Sim |Sim |
|Acesso condicional* |Sim |Sim |Sim |Sim |Sim |
> [!NOTE]
> \*O acesso condicional precisa de licenças adicionais


| |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Ponto de decisão         |A sua organização tem as licenças necessárias para atender aos requisitos empresariais de conformidade e segurança?         |
|![Ícone de próximos passos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Próximos passos         |Revise o licenciamento atual da sua organização e confirme que ele atenda todos os requisitos de negócios para conformidade e segurança.         |

Antes de habilitar qualquer um desses recursos, certifique-se de ter acesso ao Centro de Segurança e Conformidade do centro de administração do Office 365. Por padrão, os administradores de locatários têm acesso.

Pesquisa de conteúdo e descoberta eletrônica não exigem habilitação no Centro de conformidade & segurança.

<a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams
-------------------------

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. No momento, o Teams tem suporte na região das Américas, EMEA e APAC. 

> [!IMPORTANT]
> No momento, o Microsoft Teams oferece residência de dados no Reino Unido e na Índia somente para novos locatários. Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Os locatários existentes do Reino Unido e da Índia continuarão nas regiões EMEA e APAC, respectivamente, até que seja anunciado um plano de migração (previsto para 2018).

Para saber mais sobre o lançamento da residência de dados do Microsoft Teams da Índia e do Reino Unido, leia a postagem de Ansuman Acharya no blog, [Microsoft Teams launches India Data Residency, other geos coming soon](https://go.microsoft.com/fwlink/?linkid=867773).

Para ver qual região hospeda os dados de seu locatário, vá para o [Centro de administração do Office 365](https://portal.office.com/adminportal/home) > **Configurações** > **Perfil da organização**. Role para baixo até **Local dos dados**. 

![Captura de tela da tabela Local dos dados, inclusive do Microsoft Teams, no Centro de administração do Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Privacidade no Microsoft Teams
--------------------------

Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário.

Confira mais sobre nossos confiabilidade e segurança relacionados informações no [Centro de confiança do Office 365](https://go.microsoft.com/fwlink/?linkid=855779). O Teams segue os mesmos princípios e orientações da Centro de Confiabilidade do Office 365.
