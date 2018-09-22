---
title: Visão geral de segurança e conformidade no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Visão geral dos recursos de segurança e conformidade do Microsoft Teams, incluindo auditoria e relatórios, pesquisa de conteúdo de conformidade, eDiscovery e muito mais.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 331e4d600c26123079315a77d5d99f17496c12a9
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2018
ms.locfileid: "24967427"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Visão geral de segurança e conformidade no Microsoft Teams
======================================================

O Microsoft Teams está criado na nuvem empresarial de grande escala do Office 365, oferecendo os recursos avançados de segurança e conformidade que nossos clientes esperam.

O Teams tem conformidade de Camada C no lançamento. Isso inclui as seguintes normas: ISO 27001, ISO 27018, SSAE16 SOC 1 e SOC 2, HIPAA e EU Model Clauses (EUMC). Dentro da estrutura de conformidade da Microsoft, a Microsoft classifica os aplicativos e serviços do Office 365 em quatro categorias. Cada categoria é definida por compromissos de conformidade específicos que devem ser atendidos por um serviço do Office 365 ou um serviço relacionado da Microsoft para que sejam listados naquela categoria.

Os serviços das categorias de conformidade C e D que têm compromissos de conformidade líderes do setor estão habilitados por padrão. Os serviços das categorias A e B vêm com controles de ativação ou desativação para a organização inteira. Você pode encontrar detalhes em [Estrutura de conformidade para as normas e regulamentos do setor](https://go.microsoft.com/fwlink/?linkid=855777). O Microsoft Teams também dá suporte à conformidade com o Cloud Security Alliance.

O Teams também aplica uma autenticação de dois fatores para todas as equipe e organizações, registro único através do diretório ativo e criptografia de dados em trânsito e em repouso. Os arquivos ficam armazenados no SharePoint e são respaldados pela criptografia do SharePoint. As notas ficam armazenadas no OneNote e são respaldadas pela criptografia do OneNote. Os dados do OneNote são armazenados no site do SharePoint da equipe. Na guia Wiki também pode ser usada para fazer anotações e seu conteúdo também é armazenado no site do SharePoint team.

Também acrescentamos suporte para pesquisa de registros de auditoria, eDiscovery e retenção legal para canais, bate-papos e arquivos, bem como gerenciamento de aplicativos móveis com o Microsoft Intune. Vá para o Centro de conformidade & segurança do Office 365 para gerenciar essas configurações. 

## <a name="auditing-and-reporting"></a>Auditoria e relatórios

Pesquisa de log de auditoria se conecta à direita no Centro de conformidade & segurança do Office 365 e expõe capacidades para definir alertas e/ou reportar sobre eventos de auditoria, tornando disponível, exportar de carga de trabalho específicos ou evento genérico define para uso de admin e investigação, entre um cronograma de auditoria ilimitada. Todos os dados de Log de auditoria está disponíveis para a configuração de alertas dentro do Office 365 Security & Centro de conformidade, bem como para filtrar e exportar para análise adicional. Consulte este [link](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) para saber mais sobre como realizar uma pesquisa de log de auditoria para eventos do Microsoft Teams no Centro de conformidade & segurança do Office 365. 

## <a name="compliance-content-search"></a>Pesquisa de conteúdo de conformidade

Pesquisa de conteúdo pode ser usada para procurar todos os dados de equipes por meio de recursos de filtragem de rich e exportada para um contêiner específico para suporte de conformidade e litígio. Isso pode ser feito com ou sem um caso do eDiscovery. Isso permite que os administradores de conformidade coletar dados de equipes em todos os usuários, revisar e exportá-lo para processamento adicional. Consulte este [link](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) para saber mais sobre como realizar uma pesquisa de conteúdo de conformidade para conteúdo de Teams da Microsoft no Centro de conformidade & segurança do Office 365. 

Dica: O MicrosoftTeams kind pode ser usado para filtrar por meio Teams Microsoft somente conteúdo, ou seja, Chat e mensagens de canal, reuniões e chamadas. 

## <a name="ediscovery"></a>eDiscovery

A descoberta eletrônica é o aspecto eletrônico de identificar, coletar e produzir informações armazenadas eletronicamente (ESI) em resposta a uma solicitação de produção em uma ação judicial ou investigação. Recursos incluem o gerenciamento de casos, preservação, pesquisa, análise e exportação de dados de equipes. Isso inclui resumos de bate-papo, mensagens e arquivos, reuniões e chamadas. Para reuniões de equipes e chamadas, um resumo dos eventos que ocorreram na reunião e da chamada são criados e torná-los disponível no eDiscovery. 

Para obter mais detalhes sobre como fazer a descoberta eletrônica no Centro de conformidade e segurança e executar a pesquisa de conteúdo de conformidade para conteúdo de equipes, vá para os links abaixo: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Pesquisa de conteúdo](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Os clientes podem aproveitar descoberta eletrônica in-loco ou [eDiscovery Avançado] por seus requisitos (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). As diferenças entre os dois estão destacadas na tabela a seguir:


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

Durante um litígio, geralmente é necessário que todos os dados associados a um usuário (dos responsáveis) ou uma equipe é preservada imutavelmente, portanto pode ser usada como evidência para o caso. Isso é feito colocando-se um usuário (caixa de correio do usuário) ou uma equipe em retenção legal. Quando qualquer equipe dentro equipes será colocada em (subconjunto do conjunto de sites ou de caixa de correio até o destino de consultas ou conteúdo filtrado) de bloqueio In-loco ou retenção de litígio (coleção inteira de caixa de correio ou site), a retenção é colocada na caixa de correio de grupos. Isso garante que, mesmo se os usuários finais excluir ou editar as mensagens de canal são incluídas na caixa de correio de grupo, imutáveis cópias desse conteúdo são mantidos e estejam disponíveis na pesquisa eDisscovery. As retenções locais costumam ser aplicadas no contexto de um caso do eDiscovery. Consulte [Este](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) artigo para saber mais sobre preservação e isenções na segurança do Office 365 & Centro de conformidade da Ajuda. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Arquitetura de proteção de informações para as equipes da Microsoft. 

A figura a seguir indica que o fluxo de inclusão de dados de equipes para Exchange e SharePoint para mensagens e arquivos de equipes. 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

A figura a seguir indica que o fluxo de inclusão de reuniões de equipes e dados de chamada para o Exchange.

![Diagrama do fluxo de trabalho de reuniões de equipes e dados de chamada para o Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Pode haver até um atraso de 24 horas para descobrir o conteúdo de equipes.

## <a name="retention-policies"></a>Políticas de retenção

As equipes conversas são persistentes e retido para sempre por padrão. Com a introdução das políticas de retenção, admins pode configurar políticas de retenção (preservação e exclusão) no Centro de conformidade & segurança para mensagens de chat e canal de equipes. Isso ajuda as organizações a reter dados para fins de conformidade (isto é, a diretiva de preservação) por um período específico ou se livrar de dados (ou seja, a política de exclusão), se ele é considerado um passivo após um período específico. Políticas de retenção de equipes Certifique-se de que, quando você exclui dados, ele será removido de todos os locais de armazenamento de dados permanentes no serviço equipes. 

Para gerenciar políticas de retenção de equipes, use os cmdlets na segurança do Office 365 & Centro de conformidade em um **Governança de dados**e configurações > **retenção**.

Políticas de retenção de equipes têm suporte para: 
    
- Preservação: Manter dados de equipes por um período especificado e, em seguida, eu não fizer nada
- Preservação e, em seguida, excluir: manter dados de equipes por um período especificado e excluir
- Exclusão: Excluir dados de equipes após um período especificado

Políticas de retenção de equipes ainda não suportam:

- Políticas de retenção avançadas não se aplicam ao chat de equipes e locais de mensagem de canal de equipes
- Duração de menos de 30 dias

Administradores podem configurar políticas de retenção separados para mensagens de canal de equipes e chats privadas de equipes (1:1 ou 1: muitos chats). Em muitos casos, as organizações considerar os dados de bate-papo privado como mais de uma obrigação de mensagens de canal, que geralmente são mais conversas relacionados ao projeto. Configurar essas diretivas na segurança & Centro de conformidade, **Governança dados** > **retenção**. Ative **equipes mensagens de canal** e **equipes de bate-papos** e, em seguida, definir políticas de retenção desses locais (também é mostradas no diagrama a seguir). 

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

No Centro de conformidade & SSecurity, quando você configurar uma política de retenção, para equipes ou para qualquer outra carga de trabalho, você pode configurar dois tipos principais de políticas: 
- Preservação: Essas políticas garantir que seus dados seja preservados para um determinado período de tempo, não importa o que acontece nas ferramentas do usuário final. Eles garantem que dados são preservados por motivos de conformidade e expira disponíveis no eDiscovery até neste momento. Após o tempo de expiração, sua política pode indicar se deseja fazer nada ou excluir os dados. Em equipes, se você criar uma política de preservação para 7 anos, mesmo se os usuários finais excluir suas mensagens de equipes, essas mensagens são preservadas para descoberta eletrônica por 7 anos.
- Exclusão: Essas políticas garantem que os dados não são um risco para sua organização. Após o período especificado, os dados são excluídos do todo o armazenamento em equipes relevante. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Podemos incluir equipes em políticas de toda a organização? 

Não, não no momento. Você deve criar políticas específicas para mensagens de chat e canal de equipes usando a linha de local de equipes ou esses cmdlets equipes: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Esses cmdlets ter get e definir as versões também.

### <a name="are-these-retention-policies-retroactive"></a>Essas políticas de retenção são retroativas? 

Sim, eles são. Se você criar uma política de retenção para excluir os dados mais antigos do que 60 dias, ele excluirá dados de equipes criados há mais de 60 dias. 

### <a name="what-is-the-default-retention-policy"></a>Qual é a política de retenção padrão? 

Por padrão, o bate-papo equipes, de canal e dados de arquivos são mantidos indefinidamente. Um usuário pode excluir alguma coisa, mas na ausência de políticas de retenção, dados de equipes sempre serão arquivados no Exchange online mailboxes. (de usuário e de grupo) em permanecem lá para descoberta eletrônica. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Conjuntos de usuários ou equipes em uma política pode direcionar? 

Sim, você deve fazer. No Assistente de criação de política, na etapa locais, pode incluir ou excluir usuários (**chat equipes**) ou equipes (**mensagens de canal de equipes**) e criar políticas de destino para a sua organização. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>O que é a principal diferença entre usando a linha do local de caixa de correio de grupo e a linha de local de mensagens de canal de equipes em políticas de retenção? 

Se você usar a caixa de correio de grupo e linhas de local de caixa de correio do usuário para o Exchange Online, equipes de dados serão excluídas das caixas de correio especificadas. No entanto, isso só remove dados da caixa de correio. Ela não exclui os outros dados de equipes, como o serviço de bate-papos. É recomendável usar políticas de retenção de equipes para gerenciar todos os dados de equipes de forma adequada. Uma política de retenção de equipes remove dados de equipes de todos os armazenamento locais – caixas de correio, serviço de Chat, os clientes de equipes. 

Observação: O início do recurso de políticas de retenção para equipes certifica-se de que apenas as políticas de equipes excluir itens de equipes armazenados em locais de caixa de correio do Exchange (usuário ou grupo). A instalação de outras políticas em caixas de correio não pode afetar a itens de equipes. Isso era true no passado, mas foi corrigido com o lançamento do recurso de políticas de retenção. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>O que acontece com Skype para chats de interoperabilidade Business Online e equipes – eles são afetados pelas políticas de retenção?

Sim, Skype para Business Online e chats de interoperabilidade de equipes funciona da mesma maneira. Depois que o Skype para chat Business Online entra em equipes, ela se torna uma mensagem em um segmento de bate-papo de equipes e obtém incluída em uma caixa de correio apropriada. Para que o mesmo fluxo works – políticas de exclusão de equipes excluirá essas mensagens do thread equipes. No entanto, se o histórico da conversa está ativado para Skype para Business Online e do Skype para Business Online lado do cliente aqueles estão sendo salvos em uma caixa de correio, esses dados de chat não são tratados por uma política de retenção de equipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Posso fazer essas por meio do Centro de conformidade e segurança cmdlets? O que devo usar? 

Absolutamente. Você pode criar políticas de retenção de equipes usando [cmdlets do Powershell do Centro de conformidade & segurança]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Lembre-se de que não estão cmdlets do Exchange Online. Aqui estão os cmdlets que criamos para equipes. Eles siga o estilo e a nomenclatura existente da retenção cmdlets disponíveis atualmente no Centro de conformidade e segurança.

|Política|Regra|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

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

Antes de habilitar qualquer um desses recursos, verifique se que você tem acesso ao centro de conformidade & segurança no Centro de administração do Office 365. Por padrão, os administradores de locatários têm acesso.

Pesquisa de conteúdo e descoberta eletrônica não exigem habilitação no Centro de conformidade & segurança.

<a name="location-of-data-in-teams"></a>Localização dos dados no Microsoft Teams
-------------------------

Os dados no Microsoft Teams residem na região geográfica associada ao seu locatário do Office 365. Atualmente, equipes suporta as regiões da Austrália, Canadá, Índia, Japão, Reino Unido, Américas, APAC e EMEA. 

> [!IMPORTANT]
> As equipes atualmente oferece residência de dados na Austrália, Canadá, Índia, Japão e Reino Unido para os novos locatários apenas. Um novo locatário é definido como aquele que não teve nenhum usuário sequer entrando no Microsoft Teams. Inquilinos existentes da Austrália, Índia e Japão continuarão a suas equipes dos dados armazenadas na região APAC. Inquilinos existentes no Canadá e Reino Unido terão seus dados armazenados nas Américas e região EMEA, respectivamente.

Para saber mais sobre o lançamento da residência de dados do Microsoft Teams da Índia e do Reino Unido, leia a postagem de Ansuman Acharya no blog, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Para obter mais informações em residência de dados do Canadá para equipes, leia a postagem do blog de Varun Sagar, [residência de dados do Microsoft equipes inicia no Canadá, Austrália e Japão em breve](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Para saber mais sobre o lançamento do Austrália e Japão residência de dados para equipes, leia a postagem do blog de Varun Sagar, [Microsoft equipes inicia Austrália e Japão dados residência ](https://go.microsoft.com/fwlink/?linkid=867773). 

Para ver qual região armazena dados para seu locatário, vá para o [Centro de administração do Office 365](https://portal.office.com/adminportal/home) > **configurações** > **perfil da organização**. Role para baixo até **Local dos dados**. 

![Captura de tela da tabela de dados local, incluindo as equipes, no Centro de administração do Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Como funcionam as políticas de acesso condicional para equipes?
-------------------------

Microsoft Teams depende muito Exchange Online, SharePoint Online e Skype para Business Online para cenários de produtividade de núcleo, como reuniões, calendários, interoperabilidade de bate-papos e compartilhamento de arquivos. Políticas de acesso condicional que são definidas para esses aplicativos de nuvem se aplicam ao Microsoft Teams quando um usuário diretamente entra no Microsoft Teams - em qualquer cliente. 

Microsoft Teams é suportada separadamente como um aplicativo de nuvem em políticas de acesso condicional do Azure Active Directory. Políticas de acesso condicional que são definidas para o aplicativo de nuvem da Microsoft Teams se aplicam ao Microsoft Teams quando um usuário entrar. No entanto, sem as políticas corretas em outros aplicativos como o Exchange Online e SharePoint Online, os usuários ainda poderá acessar esses recursos diretamente. Para mais informações sobre como configurar uma política de acesso condicional no portal do azure, vá para: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Clientes de desktop Teams da Microsoft para Windows e Mac suportam a autenticação moderna. Autenticação moderna traz entrar com base no Azure Active Directory autenticação biblioteca (ADAL) para aplicativos cliente do Microsoft Office em todas as plataformas.

Aplicativo de área de trabalho do Microsoft Teams suporta AppLocker.  Para obter mais informações sobre os pré-requisitos do AppLocker, consulte: requisitos para usar o AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Privacidade no Microsoft Teams
--------------------------

Como cliente do Office 365, você detém e controla seus dados. A Microsoft não usa seus dados para nenhum outro fim, além de lhe fornecer o serviço ao qual você se inscreveu. Como um provedor de serviços, não examinamos seu e-mail, seus documentos nem suas equipes para publicidade ou propósitos que não estejam relacionados ao serviço. A Microsoft não tem acesso para carregar conteúdo. Assim como o OneDrive for Business e o SharePoint Online, os dados do cliente permanecem no locatário.

Veja mais informações relacionadas a confiabilidade e segurança no [Centro de Confiabilidade do Office 365](https://go.microsoft.com/fwlink/?linkid=855779). O Teams segue os mesmos princípios e orientações da Centro de Confiabilidade do Office 365.
