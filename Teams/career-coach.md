---
title: Comprar, configurar e habilitar o Career Coach para Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como comprar, configurar e habilitar o Career Coach para Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95272545080559b94faeff42d715b8f57c4d0242
ms.sourcegitcommit: ea9a0119d184179300e51f58ca4fee249c12d00a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52699352"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Comprar, configurar e habilitar o Career Coach para Microsoft Teams

O Career Coach é um Microsoft Teams para Educação, desenvolvido pelo LinkedIn, que fornece orientações personalizadas para que os alunos do ensino superior naveguem em sua jornada de carreira. O Career Coach oferece às instituições educacionais uma solução de carreira unificada para que os alunos descubram seu caminho de carreira, cresçam habilidades do mundo real e criem sua rede em um só lugar.

Saiba mais sobre [o Career Coach](https://aka.ms/career-coach).

> [!NOTE]
> Use as práticas recomendadas e dicas úteis neste guia para habilitar os recursos do Career Coach para alunos, professores e funcionários. Consulte o [artigo guia de planejamento](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) rápido.

## <a name="review-the-requirements"></a>Revisar os requisitos

Para habilitar o Career Coach para sua instituição educacional, revise o que você precisa para fazer com que o aplicativo seja executado.

**Requisitos técnicos**

  - Office 365 locatário com Azure Active Directory

  - Microsoft Teams

  - Conexões de conta do LinkedIn em Azure Active Directory

**Licenças**

  - Docentes 

  - Alunos

> [!NOTE]
> Uma licença do Corpo Docente do Técnico de Carreira deve ser atribuída ao administrador de IT concluindo a configuração.

**Dados e arquivos de sua instituição educacional**

  - Dados do catálogo de cursos

  - Campos de estudo oferecidos

  - Página do LinkedIn da instituição educacional

  - Assinatura do campus do LinkedIn Learning (preferencial)

## <a name="purchase-the-career-coach-licenses"></a>Comprar as licenças do Career Coach

O Career Coach está disponível em todo o mundo (exceto China e Rússia) para instituições de ensino superior qualificadas por meio de Inscrição para Soluções de Educação (EES), Provedores de Serviços de Nuvem (CSP) e centro de administração Microsoft 365 (web direct). Como um Microsoft Teams, os clientes devem ter Microsoft 365 A3/A5 ou Office 365 A1/A3/A5.

### <a name="assign-app-licenses-to-users"></a>Atribuir licenças de aplicativo aos usuários

Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="turn-on-linkedin-account-connections"></a>Ativar conexões de conta do LinkedIn

O Coach **de Carreira** exige que os usuários da sua instituição educacional tenham a capacidade de conectar sua conta Microsoft 365 sua conta do LinkedIn que é facilitada no Career Coach

1. Entre no Centro de administração do [Azure AD](https://aad.portal.azure.com/) com uma conta que é um administrador global da organização do Azure AD.

2. Selecione **Usuários**.

3. Na página **Usuários,** selecione **Configurações do usuário**.

4. Em conexões de conta **do LinkedIn,** permita que os usuários conectem suas contas para acessar suas conexões do LinkedIn em alguns aplicativos da Microsoft. Nenhum dado é compartilhado até que os usuários consentam em conectar suas contas.

   - Selecione **Sim** para habilitar o serviço para todos os usuários em sua instituição educacional

   - Selecione **Grupo selecionado** para habilitar o serviço apenas para um grupo de usuários selecionados em sua instituição educacional

   - Selecione **Não** para retirar o consentimento de todos os usuários em sua instituição educacional

Saiba como integrar [conexões de conta do LinkedIn Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>Configurar o Career Coach no Teams de administração

Usando as configurações de administrador no Microsoft Teams de administração, você pode configurar o Career Coach para sua instituição educacional e habilita-lo para os usuários.

## <a name="access-the-career-coach-app-settings"></a>Acessar as configurações do aplicativo Career Coach

Use a [página Gerenciar aplicativos](/microsoftteams/manage-apps) para exibir os Teams aplicativos no catálogo de aplicativos da sua instituição educacional.

1. Entre no centro de **administração Teams.**

2. Na navegação à esquerda, selecione Teams  >  **aplicativos Gerenciar aplicativos**.  

    > [!NOTE]
    > Você deve ser um administrador global ou Teams de serviço para acessar a página.

3. Pesquise ou procure **o Career Coach**.  

4. Selecione **Técnico de** Carreira e selecione **Configurações.**  

    ![mostra o aplicativo de Técnico de Carreira selecionado com a opção Configurações mostrando](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>Configurar as configurações do aplicativo de Técnico de Carreira

O Career Coach tem cinco categorias de configuração:

- [Marca e preferências](#brand-and-preferences)

- [Configuração do LinkedIn](#linkedin-configuration)

- [Catálogo de cursos](#course-catalog)

- [Campos de estudo](#fields-of-study)

- [Personalização](#customization)

> [!NOTE]
> Marca e preferências, configuração do LinkedIn,  catálogo de cursos e Campos de estudo são necessários para habilitar efetivamente o aplicativo para alunos, professores e funcionários.

#### <a name="brand-and-preferences"></a>Marca e preferências

De definir o nome, o logotipo e o idioma padrão da sua instituição educacional na página de configurações de marca e preferências.

![a seção identidade visual do Career Coach do centro de administração](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>Ícone da instituição educacional

O ícone da instituição educacional é usado em todo o Career Coach para identificar conteúdo exclusivo para sua instituição educacional, recursos de catálogo de cursos em todo o aplicativo e na seção experiências do mundo real do painel. O ícone é melhor formatado como:

 - Um PNG transparente
 - Proporção de 1:1
 - Tamanho máximo de 64 px x 64 px.

##### <a name="educational-institution-thumbnail"></a>Miniatura da instituição educacional

O ícone da instituição educacional será usado para recursos de catálogo de cursos em todo o aplicativo quando uma imagem específica não estiver disponível para um curso. O ícone é melhor formatado como:

- Um PNG
- Proporção de 16:9
- Tamanho máximo de 360 px x 200 px.

#### <a name="linkedin-configuration"></a>Configuração do LinkedIn

A configuração do LinkedIn conecta o Career Coach com dados de ex-alunos públicos do LinkedIn.

> [!NOTE]
> O Career Coach não pode ser habilitado sem a conexão de página do LinkedIn verificada.

##### <a name="add-and-confirm-the-linkedin-page"></a>Adicionar e confirmar a página do LinkedIn

Determine a página do LinkedIn da instituição educacional. Encontre a página do LinkedIn pesquisando no LinkedIn ou conectando-se a um membro da equipe de serviços de carreira para determinar a página correta a ser usada.  
  
1. Entre no centro de **administração Teams.**

1. Selecione **Teams**  >  **aplicativos Gerenciar**  >  **aplicativos Conexão** LinkedIn do Coach de  >  **Carreira.**

2. Insira a URL da página do LinkedIn da sua instituição educacional.  

3. Selecione **Aplicar**.

4. Copie a URL de verificação e compartilhe-a com a documentação de administrador de página do LinkedIn da sua instituição [educacional.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en) O link de verificação expira após 30 dias.  

   ![configurações do linkedin para o coach de carreira](media/linkedin.png)  

#### <a name="course-catalog"></a>Catálogo de cursos

O catálogo de cursos representa os cursos e aulas oferecidos aos alunos pela sua instituição educacional. Esses cursos são usados dentro do aplicativo em duas áreas:

- Os cursos são retornados como parte dos recursos de aprendizagem.  

- Cursos e metadados de curso, como descrições, são usados para ajudar os alunos a identificar suas habilidades ao carregar uma transcrição.  

Para criar o catálogo de cursos, crie uma lista de todos os cursos ministrados em sua instituição educacional e carregue-o como um arquivo CSV. O aplicativo desenha do catálogo de cursos para identificar as habilidades de um aluno a partir de sua transcrição e sugerir cursos a fazer. 

##### <a name="course-catalog-documents-formatting-and-schema"></a>Formatação e esquema de documentos do catálogo de cursos

O documento precisa estar no formato CSV com um tamanho máximo de 18 MB. O documento deve conter o título do curso **de** campos necessários , **a ID do** curso e a URL do **curso.** Incluir os campos recomendados melhora a experiência dos alunos retornando melhores resultados de pesquisa e identificação de habilidades.

> [!NOTE]
> Comece com o [documento de catálogo de cursos]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) de exemplo para começar.

A tabela a seguir mostra os itens a incluir no catálogo de cursos:


| Nome             | Status      | Tipo   | Descrição                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Obrigatório    | string | Geralmente, a id do curso (normalmente mapeia para o que é gerado na transcrição). |
| title            | Obrigatório    | string | Geralmente o título do curso.                                                      |
| sourceLink       | Obrigatório    | URL    | Link do site para a página do curso.                                               |
| description      | Recomendado | string | Texto de introdução para o curso.                                              |
| language         | Recomendado | string | Idioma do curso. Use códigos de idioma padrão.                           |
| format           | Recomendado | string | Modo de ensino, por exemplo, online, vídeo, pessoalmente.                              |
| thumbnailLink    | Recomendado | URL    | Link em miniatura para a imagem do curso.                                            |
| thumbnailAltText | Recomendado | string | Texto alt de acessibilidade para a imagem                                           |
| educationLevel   | Recomendado | string | Nível de estudo, ex. Graduando/Graduando.                                       |
| tópicos           | Recomendado | string | Tópicos ou marcas associadas às habilidades que os cursos ministram.          |

##### <a name="add-the-course-catalog"></a>Adicionar o catálogo de cursos

1. Entre no centro de **administração Teams.**

1. Selecione **Teams** &gt; **aplicativos Gerenciar** &gt; **aplicativos Career Coach** &gt; **Configurações** Catálogo de &gt; **Cursos.**  

2. Upload cursos no formato CSV.

4. Selecione **Aplicar**.

   ![a seção catálogo de cursos do aplicativo de técnico de carreira](media/course-catalog.png)

#### <a name="fields-of-study"></a>Campos de estudo

Os campos de estudo são sinônimos de áreas de interesse principais, de nível acadêmico e de grau. Esses títulos são referenciados pelos alunos quando começam a usar o aplicativo e começam a configurar seu perfil personalizado.

Adicione todos os campos de estudo disponíveis para alunos como Engenharia, Inglês, Negócios e assim por diante. A lista de campos permite que os alunos descubram campos de estudo que podem interesse a eles e adicionem sua área de foco ao perfil.

> [!NOTE]
> Comece com o [campo de exemplo do documento de](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) estudo.
##### <a name="add-the-fields-of-study"></a>Adicionar os campos de estudo

1. Entre no centro de **administração Teams.**
1. Selecione **Teams** &gt; **aplicativos Gerenciar** &gt; **aplicativos Career Coach** &gt; **Configurações** Campos &gt; **de estudo**.  

2. Upload campo de estudo no formato CSV.

3. Selecione **Aplicar**.

#### <a name="customization"></a>Personalização

O Career Coach pode ser personalizado para ser exclusivo da sua instituição educacional. A personalização dá suporte à adição de experiências ao painel. É recomendável adicionar links a placas de trabalho, eventos, escritório de serviços de carreira, eventos relacionados à carreira, clubes de alunos e qualquer outro recurso que ajude os alunos a obter experiência no mundo real.

##### <a name="add-customized-experiences"></a>Adicionar experiências personalizadas

1. Entre no centro de **administração Teams.**

1. Selecione **Teams** &gt; **aplicativos Gerenciar** &gt; **aplicativos Career Coach**  >  **Configurações** &gt; **Personalização.**

2. Adicione cada URL, um título e uma descrição curta.  
  
3. Selecione **Aplicar**.

## <a name="making-career-coach-available-to-your-organization"></a>Disponibilizar o Career Coach para sua organização

Agora que o Career Coach foi configurado para sua organização. Siga estas etapas para garantir que o Career Coach está disponível para a organização Microsoft Teams.

### <a name="enable-the-app"></a>Habilitar o aplicativo

Depois de concluir a configuração, habilita o aplicativo para alunos e usuários licenciados para que eles tenham acesso ao Career Coach.  
  
> [!NOTE]
> Você deve ter permissões de função de administrador global ou Teams de administrador.

1. Entre no centro de **administração Teams.**

1. Selecione **Teams** &gt; **aplicativos Gerenciar aplicativos** &gt; **Career Coach**.

2. Mover a alternância Status para **Permitido**.  

  > [!NOTE]
  > Permitido significa que o aplicativo está disponível para usuários em sua instituição educacional. Bloqueado significa que o aplicativo não está disponível para os alunos.

### <a name="add-career-coach-as-an-installed-app"></a>Adicionar o Career Coach como um aplicativo instalado

> [!NOTE]
> Esta etapa garante 1) que o Career Coach seja configurado corretamente para sua organização 2) que os alunos encontrem o Career Coach.

1. Entre no centro de **administração Teams.**

2. Selecione **Teams políticas de instalação de** &gt;  &gt; *aplicativos Sua política*. 

3. Em Aplicativos instalados, selecione Adicionar aplicativos.

4. No painel Adicionar aplicativos instalados, pesquise os aplicativos que você deseja instalar automaticamente para os usuários quando eles começarem a Teams. Você também pode filtrar aplicativos por política de permissão do aplicativo. Quando você escolher sua lista de aplicativos, selecione Adicionar.

### <a name="pin-the-app"></a>Fixar o aplicativo

O Pinning Career Coach torna o aplicativo mais acessível e visível para os alunos.

1. Entre no centro de **administração Teams.**

2. Selecione **Teams políticas de instalação de** &gt;  &gt; *aplicativos Sua política*. 

3. Em **Aplicativos Fixados,** escolha **Adicionar aplicativos**.

4. **Pesquise o Técnico** de Carreira e selecione **Adicionar**.

5. Escolha a ordem para que o aplicativo apareça e selecione **Salvar**.

> [!NOTE]
> Os alunos serão notificados Microsoft Teams que o Career Coach foi fixado.

Referência [Gerenciar políticas de configuração de aplicativos na Microsoft](/microsoftteams/teams-app-setup-policies) para obter detalhes adicionais.

## <a name="resources"></a>Recursos

Os recursos a seguir ajudarão você a planejar seu aplicativo de Técnico de Carreira.

- [Bem-vindo ao Microsoft Teams](Teams-overview.md)

- [Como implantar o Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Visão geral de equipes e canais no Microsoft Teams](teams-channels-overview.md)

- [Gerenciando aplicativos Microsoft Teams Admin Center](manage-apps.md)

- [Kit de Orientação Virtual Online](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [Limites e especificação de Teams canais](limits-specifications-teams.md)

- [Iniciando o treinamento de administrador para Microsoft Teams](ITAdmin-readiness.md)

- [Solução de problemas do Teams](/microsoftteams/troubleshoot/teams-welcome)

- [Gerenciar políticas de permissões de aplicativo no Microsoft Teams](teams-app-permission-policies.md)
