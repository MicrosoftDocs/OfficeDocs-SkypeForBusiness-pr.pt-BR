---
title: Gerenciar q&A em reuniões do Teams
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
audience: Admin
appliesto:
- Microsoft Teams
description: Saiba mais sobre como os administradores de TI podem configurar, usar e gerenciar q&A no Teams Q&A para uma abordagem estruturada para coletar perguntas, organizar discussões, excluir mensagens individuais, usar idiomas disponíveis e entender o ciclo de vida dos dados, bem como políticas de exclusão e retenção de dados.
ms.openlocfilehash: 3d85dbe4c9035a9de0ccb47557735bb797bdf244
ms.sourcegitcommit: 94e3f5e8dcfe8b3098ed8de2e4397e2338038f03
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "69177717"
---
# <a name="manage-qa-in-teams-meetings"></a>Gerenciar q&A em reuniões do Teams

Q&A permite que os apresentadores tirem perguntas dos participantes e respondam em tempo real. Esse recurso é mais adequado para reuniões grandes e estruturadas – como Prefeituras, Webinars, Todas as Mãos e treinamentos.

Este artigo descreve como gerenciar políticas de Q&A e de nível de usuário, que determinam se um organizador pode habilitar o Teams Q&A em suas reuniões.

## <a name="prerequisites"></a>Pré-requisitos

- Verifique se você não bloqueou o acesso aos [IPs e URLs do Yammer.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
- Para permitir que os usuários em sua organização adicionem Q&A às reuniões do Teams, você precisa confirmar que as entradas para o serviço Office 365 Yammer estão habilitadas no Azure Active Directory. Siga as etapas abaixo para confirmar se as entradas estão habilitadas:
  - Acesse o centro  >  de **administração Azure AD****Todos os serviços** > **Aplicativos Empresariais** >  Office 365 **Propriedades** **do Yammer** > .
  - Para a opção **Habilitado para usuários entrarem?** selecione **Sim** , se necessário.
- Verifique se você não bloqueou o aplicativo Q&A (Nativo) em [aplicativos do Teams](/MicrosoftTeams/manage-apps)

## <a name="who-can-use-qa"></a>Quem pode usar q&A

Q&A pode ser usado pelos seguintes tipos de usuário:

- Usuário regular: um usuário com Microsoft 365 credenciais em seu locatário.
- Usuário federado — um usuário com Microsoft 365 credenciais para um locatário diferente.
- Usuário convidado— Todos os convidados que você adicionar ao seu Microsoft Teams, SharePoint ou Azure Active Directory.

> [!NOTE]
> Q&A não está disponível no GCC.

Quando os administradores habilitam o Q&A, os usuários com a [função organizador](https://aka.ms/GetQnA) podem ativar o Q&A ao criar ou atualizar reuniões. Por meio das opções de reunião do Teams e do Outlook, os organizadores também podem remover q&A de reuniões em que ele foi adicionado anteriormente para impedir que os participantes usem o recurso.
> [!NOTE]
> Q&A não estará disponível para exibir somente participantes que ingressarem após a capacidade da reunião.

## <a name="use-the-teams-admin-center-to-manage-qa"></a>Usar o centro de administração do Teams para gerenciar o Q&A

Sua organização pode ter requisitos para limitar quais organizadores podem ativar o Q&A. Você pode usar o centro de administração do Teams para gerenciar quais organizadores podem ativar o Q&A em grandes reuniões.
Siga estas etapas para controlar quais organizadores podem usar q&A:

1. No centro de administração do Teams, acesse [**Políticas de Reunião**](/meeting-policies-participants-and-guests) de **Reuniões** > 
2. Selecione uma política existente ou crie uma nova e dê a ela um nome como "Sem Q&A para esses organizadores"
3. Role até a seção chamada **"Participantes & Convidados",** selecione desabilitar para a configuração **"Experiência de Resposta & pergunta"** e salve a política
4. Atribuir a política a grupos, usuários finais ou assinaturas específicos do M365 que você deseja impedir de configurar o Q&A

## <a name="use-powershell-to-manage-qa"></a>Usar o PowerShell para gerenciar q&A

Sua organização pode ter requisitos para limitar quais organizadores podem ativar o Q&A. Você pode usar o PowerShell para gerenciar quais organizadores podem ativar o Q&A em grandes reuniões.

Exemplo de comando do PowerShell para Habilitar o Q&A:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -QnAEngagementMode Enabled
```

## <a name="delete-an-individual-message-from-qa-in-teams"></a>Excluir uma mensagem individual do Q&A no Teams

Para excluir uma pergunta ou resposta postada no aplicativo Q&A, siga estas etapas:

1. Faça logon no Exchange Administração Center como administrador global.
2. Acesse **Caixas de correio destinatários**  >  e pesquise pelo nome do usuário que organizou a reunião.
3. Selecione o organizador da reunião e clique em **Gerenciar delegação de caixa de correio**. Na seção **Ler e gerenciar** , selecione **Editar Adicionar** > **permissões**.
4. Adicione-se como representante do organizador da reunião e selecione Salvar.
5. Abra Calendário do Outlook no Outlook Web App (não na área de trabalho) e selecione **Adicionar calendário** e, em seguida **, Adicionar do diretório**.
6. Pesquise o organizador da reunião e adicione seu calendário aos **meus calendários**. As reuniões para o usuário selecionado agora serão mostradas em seu calendário.
7. Em seu calendário, localize a reunião para a qual você deseja excluir conteúdo, abra o registro da reunião e selecione **Conversar com os participantes**. Selecionar o chat com os participantes abrirá o chat da reunião no Teams.
8. Navegue até o aplicativo Q&A na barra de aplicativos do Teams.
9. Encontre quaisquer perguntas ou respostas que você deseja excluir e selecione Excluir.
10. Depois de concluir a exclusão do conteúdo, volte para o Centro de Administração do Exchange e remova-se como representante do organizador da reunião.

> [!NOTE]
> Se você excluir uma pergunta antes de remover as respostas, a primeira resposta à pergunta se tornará a pergunta.
>
> Para evitar isso, siga estas etapas em ordem:
>
> 1. Identificar a pergunta que você gostaria de excluir
> 2. Excluir as respostas para a pergunta
> 3. Excluir a pergunta

## <a name="available-languages-for-yammer-versus-teams"></a>Idiomas disponíveis para Yammer versus Teams

O Q&A será padrão para o idioma do usuário para o Teams. Quando houver uma diferença nos idiomas disponíveis para Teams versus Yammer, o seguinte padrão de idioma ocorrerá:

- Idioma primário mais próximo— o Yammer será padrão para o idioma primário mais próximo, se disponível. Por exemplo, o Yammer não fornece uma versão canadense francesa (fr-CA), portanto, ele exibirá conteúdo em francês (fr-FR) em vez disso.
- Idioma sem suporte — se o idioma não for fornecido pelo Yammer, o Yammer será padrão para o inglês dos EUA (en-US).

## <a name="ediscovery"></a>Descoberta Eletrônica

A descoberta eletrônica para Q&A funcionará da mesma forma que a descoberta eletrônica para qualquer outro conteúdo do Yammer.

- Se você usar o Teams Q&A no aplicativo teams do locatário, esse conteúdo estará disponível em descoberta eletrônica, independentemente da configuração ou existência de sua rede Yammer. Para usar a descoberta eletrônica para conteúdo padrão do Yammer, sua rede Yammer precisa estar no [Modo Nativo](/yammer/configure-your-yammer-network/overview-native-mode).
- Ao executar a descoberta eletrônica, você pode determinar se as mensagens foram geradas no Yammer ou por meio do Q&A no Teams. Na seção Metadados de Arquivo, você pode encontrar essas informações no campo Classe de Item.
- Se sua organização usar o Teams Q&A, alimentado pelo Yammer, o conteúdo gerado pelo Q&A será considerado conteúdo do Yammer e será detectável. Para obter mais informações sobre a descoberta eletrônica em Microsoft 365 aplicativos, consulte [soluções de descoberta eletrônica no Microsoft 365.](/microsoft-365/compliance/ediscovery)
- Se o organizador da reunião habilitar a postagem anônima, as perguntas que os participantes postarem serão ingeridas na caixa de correio do organizador para descoberta eletrônica.

## <a name="data-storage"></a>Armazenamento de Dados

Q&As mensagens criadas como parte da reunião são armazenadas como mensagens do Yammer. Essas mensagens são armazenadas no Yammer e ingeridas para descoberta eletrônica.
Os arquivos são sempre armazenados no SharePoint, que manipula todas as políticas e locais de descanso de dados.

As diretrizes a seguir explicam como os dados de mensagens são armazenados:

- Q&Um conteúdo é pesquisável por meio de descoberta eletrônica e Advanced eDiscovery no nível do usuário.
- Os dados de mensagem (que incluem conteúdo de mensagem) serão armazenados no América do Norte ou na UE por padrão (dependendo da localização da rede Yammer do cliente).
- Para locatários que não têm uma rede Yammer existente, a rede Q&A Yammer será criada na região Estados Unidos Yammer. As mensagens da sua organização para q&A sempre serão armazenadas nos EUA.
- Semelhante às guias do OneNote, a remoção do Q&A de uma reunião não exclui os dados da reunião. A remoção do Q&A da reunião só remove o acesso aos dados da reunião. Se você adicionar a guia Q&A novamente, verá todas as conversas da reunião novamente.

## <a name="gdpr-for-qa-in-teams"></a>GDPR para Q&A no Teams

Quando você conclui uma Solicitação de Assunto de Dados por meio do Centro de Administração Microsoft 365, ela remove automaticamente as informações de contato dos usuários de todo o conteúdo no Q&A.

## <a name="data-lifecycle-for-qa-in-teams"></a>Ciclo de vida de dados para Q&A no Teams

O ciclo de vida dos dados gerados pelo Q&A no Teams depende das configurações de retenção de dados do Yammer no Centro de Conformidade. Se você excluir duramente todos os usuários na reunião que receberam uma cópia das mensagens Q&A em seu fragmento de substrato por meio do Azure Active Directory, o Yammer excluirá sua cópia do conteúdo Q&A para essa reunião dentro de 30 dias após a exclusão do usuário.

## <a name="retention-and-deletion"></a>Retenção e exclusão

A retenção de conteúdo segue as políticas de retenção definidas para o Yammer – independentemente de você ter políticas diferentes definidas para o Yammer e o Teams.

> [!NOTE]
> Se sua Rede Yammer não estiver no Modo Nativo, as políticas criadas aqui se aplicarão apenas aos dados do Teams Q&A. No Modo Nativo, todos os usuários do Yammer estão no Azure Active Directory (Azure AD), todos os grupos são Microsoft 365 grupos e todos os arquivos são armazenados no SharePoint Online.

## <a name="faq"></a>Perguntas frequentes

**P: Como fazer exportar conteúdo Q&A?**

**Um:** Q&Um conteúdo é armazenado no Centro de conformidade do Microsoft 365 e acessado por meio da descoberta eletrônica. As iterações futuras incluirão um relatório de destaques da reunião e a funcionalidade de exportação para os organizadores da reunião.

**P: O Q&Um dá suporte Microsoft 365 recursos multi-geográficos?**

**Um:** Q&A atualmente não dá suporte a Microsoft 365 recursos multi-geográficos. Q&Um dados será armazenado no América do Norte ou na UE por padrão (dependendo da localização da rede Yammer do cliente).

**P: Onde posso aprender mais sobre reuniões estruturadas?**

**Um:** Siga [estas práticas recomendadas](/MicrosoftTeams/quick-start-meetings-live-events) para hospedar grandes reuniões bem-sucedidas no Microsoft Teams.

**P: Qual é a diferença entre configurar o Q&A por meio da loja de aplicativos do Teams em vez de usar opções de reunião?**

**Um:** Simplificamos a habilitação do Q&A por meio de Opções de Reunião.A partir de agosto de 2022, o aplicativo Q&A na loja de aplicativos do Teams não terá mais suporte, portanto, o Q&A só deve ser habilitado por meio de Opções de Reunião. Se você for o organizador de reuniões em que o Q&A foi habilitado por meio da loja de aplicativos do Teams, remova o aplicativo Q&A e, em vez disso, habilite apenas por meio de Opções de Reunião.

**P: Por que estou vendo dois ícones do Q&A na minha reunião?**

**Um:** Você está vendo dois ícones Q&A em sua reunião porque o Q&A também foi habilitado por meio de Opções de Reunião. Remova o aplicativo Q&A que foi adicionado por meio do teams App Store usando as instruções abaixo. Faça isso por todas as suas reuniões em que você havia adicionado anteriormente q&A por meio da loja de aplicativos do Teams.

**Como remover o aplicativo Q&A que foi adicionado da loja de aplicativos do Teams.**

1. Na Área de Trabalho do Teams, participe da reunião em que você adicionou anteriormente q&A.

2. No painel superior, selecione a segunda ocorrência do ícone Q&A na janela Reunião do Teams – esta é a experiência Q&A que foi adicionada por meio do App Store do Teams.

3. Com a guia Q&A selecionada aberta, clique nas reticências e clique em "Remover". Isso removerá a experiência Q&A que foi adicionada por meio do repositório de aplicativos do Teams.

4. Clique em "Remover" para remover permanentemente a experiência Q&A adicionada por meio da loja de aplicativos do Teams.

> [!NOTE]
> Somente o aplicativo Q&A adicionado por meio da loja de aplicativos do Teams terá uma reticência para remover o aplicativo Q&A. O Q&Uma experiência habilitada por meio de Opções de Reunião não terá uma reticência e não poderá ser removido daqui.

É isso! Agora há apenas uma experiência de Q&A – alimentada por Opções de Reunião. O aplicativo Q&A adicionado por meio da loja de aplicativos do Teams é removido.
