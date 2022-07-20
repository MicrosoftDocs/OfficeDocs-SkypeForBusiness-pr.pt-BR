---
title: Gerenciar Q&A em reuniões do Teams
author: wlibebe
ms.author: wlibebe
ms.reviewer: sameer.sitaram
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
description: Saiba mais sobre como os administradores de TI podem configurar, usar e gerenciar q&A no Teams Q&A para uma abordagem estruturada para coletar perguntas, organizar discussões, excluir mensagens individuais, usar idiomas disponíveis e entender o ciclo de vida de dados, bem como políticas de retenção e exclusão de dados.
ms.openlocfilehash: 3ffdc4f48c43bef2d1d342983a63612c91bc40a9
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880425"
---
# <a name="manage-qa-in-teams-meetings"></a>Gerenciar Q&A em reuniões do Teams

As&A permitem que os apresentadores tirem dúvidas dos participantes e respondam-nas em tempo real. Esse recurso é mais adequado para reuniões grandes e estruturadas, como Prefeituras, Webinars, Todas as Mãos e treinamentos.

Este artigo descreve como gerenciar as&A e as políticas de nível de usuário, que determinam se um organizador pode habilitar o Teams Q&A em suas reuniões.

## <a name="prerequisites"></a>Pré-requisitos

- Verifique se você não bloqueou o acesso aos [IPs e URLs do Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Para permitir que os usuários em sua organização adicionem Q&A às reuniões do Teams, você precisa confirmar se as entradas para o serviço Office 365 Yammer estão habilitadas no Azure Active Directory. Siga as etapas abaixo para confirmar se as entradas estão habilitadas:
  - Acesse o centro **de administração Azure AD todos** > **os serviços** > **Aplicativos Empresariais** >  **Office 365 Propriedades do Yammer** > .
  - Para a **opção Habilitada para os usuários se conectarem,** selecione **Sim** , se necessário.

## <a name="who-can-use-qa"></a>Quem pode usar Q&A

As&A podem ser usadas pelos seguintes tipos de usuário:

- Usuário normal – um usuário com credenciais do Microsoft 365 em seu locatário.
- Usuário federado – um usuário com credenciais do Microsoft 365 para um locatário diferente.
- Usuário convidado – todos os convidados que você adicionar ao Microsoft Teams, SharePoint ou Azure Active Directory.

> [!NOTE]
> As&A não estarão disponíveis para Exibir Somente Os Participantes que ingressarem após a capacidade da reunião.

Quando os administradores habilitam o Q&A, os usuários [](https://aka.ms/GetQnA) com a função organizador podem ativar o Q&A ao criar ou atualizar reuniões. Por meio das opções de reunião do Teams e do Outlook, os organizadores também podem remover o Q&A das reuniões em que ele foi adicionado anteriormente para impedir que os participantes usem o recurso.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Usar o centro de administração do Teams para gerenciar o Q&A

Sua organização pode ter requisitos para limitar quais organizadores podem ativar o Q&A. Você pode usar o centro de administração do Teams para gerenciar quais organizadores podem ativar o Q&A em grandes reuniões.
Siga estas etapas para controlar quais organizadores podem usar o Q&A:

1. No centro de administração do Teams, acesse Políticas **de Reunião** > [**de Reuniões**](/meeting-policies-participants-and-guests)
2. Selecione uma política existente ou crie uma nova e dê a ela um nome como "Nenhum Q&A para esses organizadores"
3. Role até a seção **chamada "Participantes & Convidados"**, selecione desabilitar para a configuração "Experiência de resposta & perguntas" e salve **a** política
4. Atribua a política a grupos específicos do M365, usuários finais ou assinaturas que você deseja impedir de configurar o Q&A

## <a name="use-powershell-to-manage-qa"></a>Usar o PowerShell para gerenciar o Q&A

Sua organização pode ter requisitos para limitar quais organizadores podem ativar o Q&A. Você pode usar o PowerShell para gerenciar quais organizadores podem ativar o Q&A em grandes reuniões.

Exemplo de comando do PowerShell para Habilitar Q&A:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Excluir uma mensagem individual do Q&A no Teams

Para excluir uma pergunta ou resposta postada no aplicativo Q&A, siga estas etapas:

1. Faça logon no Exchange Administração Center como administrador global.
2. Vá para **Caixas de Correio****de Destinatários** >  e pesquise pelo nome do usuário que organizou a reunião.
3. Selecione o organizador da reunião e clique em Gerenciar **delegação de caixa de correio**. Na seção **Ler e gerenciar** , selecione **Editar** > **Adicionar permissões**.
4. Adicione-se como representante do organizador da reunião e selecione Salvar.
5. Abra Calendário do Outlook no Outlook Web App (não na área de trabalho) e selecione Adicionar **calendário** e, em seguida **, Adicione do diretório**.
6. Pesquise o organizador da reunião e adicione seu calendário **a Meus calendários**. As reuniões para o usuário selecionado agora serão mostradas em seu calendário.
7. Em seu calendário, localize a reunião para a qual você deseja excluir o conteúdo, abra o registro da reunião e selecione **Chat com os participantes**. Selecionar o chat com os participantes abrirá o chat da reunião no Teams.
8. Navegue até o aplicativo Q&A na barra de aplicativos do Teams.
9. Localize as perguntas ou respostas que você deseja excluir e selecione Excluir.
10. Quando terminar de excluir o conteúdo, volte para o Exchange Administração Center e remova-se como representante do organizador da reunião.

> [!NOTE]
> Se você excluir uma pergunta antes de remover as respostas, a primeira resposta para a pergunta se tornará a pergunta.
>
> Para evitar isso, siga estas etapas na ordem:
>
> 1. Identificar a pergunta que você deseja excluir
> 2. Excluir as respostas à pergunta
> 3. Excluir a pergunta

## <a name="available-languages-for-yammer-versus-teams"></a>Idiomas disponíveis para Yammer versus Teams

O Q&A usará como padrão o idioma do usuário para o Teams. Quando houver uma diferença nos idiomas disponíveis para o Teams versus o Yammer, ocorrerão os seguintes padrões de idioma:

- Idioma primário mais próximo — o Yammer usará como padrão o idioma primário mais próximo, se disponível. Por exemplo, o Yammer não fornece uma versão francesa canadense (fr-CA), portanto, ele exibirá o conteúdo em francês (fr-FR) em vez disso.
- Idioma sem suporte — se o idioma não for fornecido pelo Yammer, o Yammer usará como padrão o inglês dos EUA (en-US).

## <a name="ediscovery"></a>Descoberta Eletrônica

A Descoberta Eletrônica para Q&A funcionará da mesma forma que a Descoberta Eletrônica para qualquer outro conteúdo do Yammer.

- Se você usar o Teams Q&A no aplicativo Teams do locatário, esse conteúdo estará disponível na Descoberta Eletrônica, independentemente da configuração ou da existência de sua rede do Yammer. Para usar a Descoberta Eletrônica para conteúdo padrão do Yammer, sua rede do Yammer precisa estar no [Modo Nativo](/yammer/configure-your-yammer-network/overview-native-mode).
- Ao executar a Descoberta Eletrônica, você pode determinar se as mensagens foram geradas no Yammer ou por meio de Q&A no Teams. Na seção Metadados de Arquivo, você pode encontrar essas informações no campo Classe de Item.
- Se sua organização usar o Teams Q&A, da plataforma Yammer, o conteúdo gerado pelo Q&A será considerado conteúdo do Yammer e será detectável. Para obter mais informações sobre a Descoberta Eletrônica em aplicativos do Microsoft 365, consulte [soluções de Descoberta Eletrônica no Microsoft 365.](/microsoft-365/compliance/ediscovery)
- Se o organizador da reunião habilitar a postagem anônima, as perguntas que os participantes postarem serão ingeridos na caixa de correio do organizador para Descoberta Eletrônica.

## <a name="data-storage"></a>Armazenamento de dados

P&Mensagens criadas como parte da reunião são armazenadas como mensagens do Yammer. Essas mensagens são armazenadas no Yammer e ingeridos para Descoberta Eletrônica.
Os arquivos são sempre armazenados no SharePoint, que manipula todas as políticas e locais de repouso de dados.

As diretrizes a seguir explicam como os dados de mensagens são armazenados:

- P&Um conteúdo é pesquisável por meio da Descoberta Eletrônica e Advanced eDiscovery no nível do usuário.
- Os dados da mensagem (que incluem o conteúdo da mensagem) serão armazenados no América do Norte ou na UE por padrão (dependendo do local de rede do Yammer do cliente).
- Para locatários que não têm uma rede existente do Yammer, a Q&uma rede do Yammer será criada na região Estados Unidos Yammer. As mensagens da sua organização para Q&A sempre serão armazenadas nos EUA.
- Semelhante às guias do OneNote, remover o Q&A de uma reunião não exclui os dados da reunião. A remoção&A da reunião remove apenas o acesso aos dados da reunião. Se você adicionar a guia Q&A novamente, verá todas as conversas da reunião novamente.

## <a name="gdpr-for-qa-in-teams"></a>RGPD para Q&A no Teams

Quando você conclui uma Solicitação de Entidade de Dados por meio do Administração Microsoft 365 Center, ela remove automaticamente as informações de contato dos usuários de todo o conteúdo no Q&A.

## <a name="data-lifecycle-for-qa-in-teams"></a>Ciclo de vida de dados para&A no Teams

O ciclo de vida dos dados gerados pelo Q&A no Teams depende das configurações de Retenção de Dados do Yammer no Centro de Conformidade. Se você excluir permanentemente todos os usuários da reunião que receberam uma cópia das mensagens do Q&A em seu fragmento de substrate por meio do Azure Active Directory, o Yammer excluirá sua cópia do conteúdo do Q&A para essa reunião dentro de 30 dias após a exclusão do usuário.

## <a name="retention-and-deletion"></a>Retenção e exclusão

A retenção de conteúdo segue as políticas de retenção definidas para o Yammer, independentemente de você ter políticas diferentes definidas para o Yammer e o Teams.

> [!NOTE]
> Se sua Rede do Yammer não estiver no Modo Nativo, as políticas criadas aqui serão aplicadas somente aos dados do Teams Q&A. No Modo Nativo, todos os usuários do Yammer estão no Azure Active Directory (Azure AD), todos os grupos são grupos do Microsoft 365 e todos os arquivos são armazenados no SharePoint Online.

## <a name="faq"></a>Perguntas frequentes

**P: Como fazer exportar O&conteúdo A?**

**Um:** O&um conteúdo é armazenado no Centro de conformidade do Microsoft 365 e acessado por meio da Descoberta Eletrônica. As iterações futuras incluirão um relatório de destaques de reunião e a funcionalidade de exportação para os organizadores da reunião.

**P: O Q&A dá suporte a recursos multigeográficos do Microsoft 365?**

**Um:** As&A atualmente não dão suporte a recursos multigeográficos do Microsoft 365. P&Dados A serão armazenados no América do Norte ou na UE por padrão (dependendo do local de rede do Yammer do cliente).

**P: Onde posso saber mais sobre reuniões estruturadas?**

**Um:** Siga estas [práticas recomendadas para](/MicrosoftTeams/quick-start-meetings-live-events) hospedar grandes reuniões bem-sucedidas no Microsoft Teams.

**P: Qual é a diferença entre configurar o Q&A por meio da Loja de Aplicativos do Teams em vez de usar as Opções de Reunião?**

**Um:** Simplificamos a habilitação do Q&A por meio de Opções de Reunião. A partir de agosto de 2022, o aplicativo Q&A na loja de aplicativos do Teams não terá mais suporte, portanto, o Q&A só deve ser habilitado por meio de Opções de Reunião. Se você for o organizador de reuniões em que o Q&A foi habilitado por meio da loja de aplicativos do Teams, remova o aplicativo Q&A e, em vez disso, habilite apenas por meio das Opções de Reunião.

**P: Por que estou vendo dois ícones de Q&A em minha reunião?**

**Um:** Você está vendo dois ícones de Q&A em sua reunião porque o Q&A também foi habilitado por meio de Opções de Reunião. Remova o aplicativo Q&A que foi adicionado por meio do teams App Store usando as instruções abaixo. Faça isso em todas as suas reuniões em que você adicionou o Q&A por meio da loja de aplicativos do Teams.

**Como remover o aplicativo Q&Um que foi adicionado da loja de aplicativos do Teams.**

1. No Teams Desktop, participe da reunião em que você adicionou o Q&A.

2. No painel superior, selecione a segunda ocorrência do ícone Q&A na janela Reunião do Teams – essa é a experiência do Q&A que foi adicionada por meio do Teams App Store.

3. Com a guia Q&A selecionada, clique nas reticências e clique em "Remover". Isso removerá o Q&uma experiência que foi adicionada por meio da loja de aplicativos do Teams.

4. Clique em "Remover" para remover permanentemente o Q&uma experiência que foi adicionada por meio da loja de aplicativos do Teams.

> [!NOTE]
> Somente o aplicativo Q&A adicionado por meio da loja de aplicativos do Teams terá reticências para remover o aplicativo Q&A. O Q&uma experiência habilitada por meio de Opções de Reunião não terá reticências e não poderá ser removido daqui.

É isso! Agora há apenas um Q&uma experiência – da plataforma Opções de Reunião. O aplicativo Q&A adicionado por meio da loja de aplicativos do Teams foi removido.
