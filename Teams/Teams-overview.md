---
title: "Visão geral do Microsoft Teams | Suporte da Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Conheça o Microsoft Teams, sua infraestrutura e a utilização do Teams com o Office 365."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 10d4297f8b4cfcf3bf28a2a64177f078130166eb
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2017
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="872c3-103">Visão geral do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="872c3-103">Overview of security and compliance in Microsoft Teams</span></span>
===========================

| | |
|---------|---------|
| <iframe src="//videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false&height=415&width=740" frameborder= "0" marginwidth= "0" marginheight= "0" scrolling= "no" allowfullscreen= "" style="width: 740px; height: 415px;"></iframe>   |         |


<span data-ttu-id="872c3-104">O Microsoft Teams reúne toda a amplitude e a profundidade do Office 365 para oferecer um verdadeiro hub baseado em bate-papo para trabalhos em equipe e oferecer aos clientes a oportunidade de criar um ambiente mais aberto, fluido e digital.</span><span class="sxs-lookup"><span data-stu-id="872c3-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="872c3-105">O Microsoft Teams é desenvolvido com as tecnologias existentes da Microsoft, reunidas aos grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="872c3-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="872c3-106">Fora da caixa, o Teams aproveita as identidades armazenadas no Azure Active Directory (Azure AD) e se integra aos outros serviços do Office 365 para criar um site online do SharePoint e uma caixa de correio de grupo do Exchange Online para cada equipe criada.</span><span class="sxs-lookup"><span data-stu-id="872c3-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="872c3-107">O recurso persistente de bate-papo do Teams é proporcionado por um serviço de bate-papo que interage com o substrato do Office 365, abordando muitos dos recursos internos do Office 365, como arquivamento e o eDiscovery para os dados que estão sendo trocados no Teams.</span><span class="sxs-lookup"><span data-stu-id="872c3-107">The Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="872c3-108">O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="872c3-108">As mentioned, Microsoft Teams calling and meetings experience is built on the next generation cloud based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="872c3-109">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="872c3-109">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry and quality diagnostics.</span></span>

<span data-ttu-id="872c3-110">Para ampliar os recursos do Teams, use Conectores, Guias e Bots, disponíveis como [Aplicativos](https://go.microsoft.com/fwlink/?linkid=854629), para trazer informações externas, conteúdo e interações de bots inteligentes para o Teams.</span><span class="sxs-lookup"><span data-stu-id="872c3-110">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="872c3-111">Infraestrutura do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="872c3-111">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="872c3-112">O Teams é desenvolvido com as tecnologias existentes da Microsoft, reunidas aos grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="872c3-112">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="872c3-113">Alimentado pela nuvem da Microsoft, as organizações podem esperar um excelente desempenho e confiabilidade ao aproveitar o Teams como parte da sua história de colaboração.</span><span class="sxs-lookup"><span data-stu-id="872c3-113">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="872c3-114">Fora da caixa, uma equipe criada no Teams criará um grupo do Office 365, um site do SharePoint Online (completo, com uma biblioteca de documentos) e uma caixa de correio de grupo do Exchange Online, que será usada pelo Teams ara armazenar informações, como convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="872c3-114">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="872c3-115">Uma equipe pode ser criada usando os Grupos existentes do Office 365, permitindo que as assinaturas de grupo existentes e os conteúdos armazenados no SharePoint Online e no Exchange Online sejam transferidos ao Teams.</span><span class="sxs-lookup"><span data-stu-id="872c3-115">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="872c3-116">O bate-papo persistente do Teams é proporcionado por um serviço de bate-papo que interage com o do Office 365, abordando muitos dos recursos internos do Office 365, como arquivamento e o eDiscovery para os dados que estão sendo trocados no Teams.</span><span class="sxs-lookup"><span data-stu-id="872c3-116">Teams persistent chat is provided by a chat service that interacts with Office 365, surfacing many of the built-in Office 365 capabilities such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="872c3-117">Para complementar o recurso do Teams como uma plataforma de bate-papo persistente onde ocorrem conversas informais e em tempo real, o Teams também oferece uma experiência de reunião construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="872c3-117">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="872c3-118">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="872c3-118">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry and quality diagnostics.</span></span>

<span data-ttu-id="872c3-119">Os Grupos do Office 365 aproveitam as identidades armazenadas no Azure Active Directory (Azure AD) e, assim, todos os recursos de autenticação e autorização do Azure AD, como suporte para autenticação multifator (MFA), estão prontamente disponíveis para uso no Teams.</span><span class="sxs-lookup"><span data-stu-id="872c3-119">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="872c3-120">Microsoft Teams e Office 365</span><span class="sxs-lookup"><span data-stu-id="872c3-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="872c3-121">Os diferentes grupos têm necessidades variadas com base no seu papel funcional e estilo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="872c3-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="872c3-122">O Office 365 foi projetado para o estilo de trabalho exclusivo de cada grupo e inclui aplicativos integrados e específicos para o propósito, incluindo:</span><span class="sxs-lookup"><span data-stu-id="872c3-122">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="872c3-123">Outlook para e-mails profissionais, agora com a funcionalidade de grupos</span><span class="sxs-lookup"><span data-stu-id="872c3-123">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="872c3-124">SharePoint para sites e portais, serviços de conteúdo inteligente, automação de processos comerciais e pesquisa empresarial</span><span class="sxs-lookup"><span data-stu-id="872c3-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="872c3-125">Yammer para impulsionar as conexões em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="872c3-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="872c3-126">Skype for Business como o suporte principal de voz e vídeos empresariais</span><span class="sxs-lookup"><span data-stu-id="872c3-126">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="872c3-127">E agora, p Microsoft Teams, o novo espaço de trabalho baseado em bate-papo do Office 365</span><span class="sxs-lookup"><span data-stu-id="872c3-127">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="872c3-128">Seguem alguns casos de uso comuns de cada aplicativo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="872c3-128">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="872c3-129">Para obter orientações de uso detalhadas, acesse a [Biblioteca de Produtividade FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).</span><span class="sxs-lookup"><span data-stu-id="872c3-129">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Ícone do Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="872c3-131">Aproveitado por usuários e equipes que desejam colaborar em tempo real com o mesmo grupo de pessoas.</span><span class="sxs-lookup"><span data-stu-id="872c3-131">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="872c3-132">Ajuda as equipes que desejam iterar rapidamente em um projeto, enquanto compartilham arquivos e colaboram em materiais compartilhados.</span><span class="sxs-lookup"><span data-stu-id="872c3-132">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="872c3-133">Permite que usuários que desejam se conectar uma grande variedade de ferramentas em seu espaço de trabalho (como Planner, Power BI, GitHub, etc.).</span><span class="sxs-lookup"><span data-stu-id="872c3-133">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Ícone do Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="872c3-135">Aproveitado por usuários que preferem colaborar no ambiente familiar de e-mails e/ou de uma forma mais formal e estruturada.</span><span class="sxs-lookup"><span data-stu-id="872c3-135">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="872c3-136">Fornece processos comerciais específicos que exigem o uso de e-mails para transferir documentos e informações dentro e fora dos limites corporativos.</span><span class="sxs-lookup"><span data-stu-id="872c3-136">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="872c3-137">Comunica e se conecta com usuários que estão fora de grupos de trabalho ou organizações imediatos.</span><span class="sxs-lookup"><span data-stu-id="872c3-137">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Ícone do Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="872c3-139">Aproveitado para ajudar a conectar usuários em toda a organização para se organizarem em comunidades de prática e compartilharem boas práticas.</span><span class="sxs-lookup"><span data-stu-id="872c3-139">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="872c3-140">Melhora os fluxos de trabalho multifuncionais através de uma plataforma aberta e transparente baseada em feed</span><span class="sxs-lookup"><span data-stu-id="872c3-140">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="872c3-141">Promove o envolvimento entre executivos e funcionários através de conversas bidirecionais entre a liderança e a base mais ampla de funcionários</span><span class="sxs-lookup"><span data-stu-id="872c3-141">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="872c3-142">Incentiva sua força de trabalho da linha de frente a compartilhar e receber conhecimentos e expertise</span><span class="sxs-lookup"><span data-stu-id="872c3-142">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Ícone do Skype for Business.](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="872c3-144">Aproveitado para comunicação e colaboração em tempo real, interna e externamente com clientes/parceiros.</span><span class="sxs-lookup"><span data-stu-id="872c3-144">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="872c3-145">Proporciona reuniões com áudio, vídeo e conteúdo, com equipes grandes ou pequenas (incluindo assembleias com até 10.000 participantes).</span><span class="sxs-lookup"><span data-stu-id="872c3-145">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="872c3-146">Oferece funcionalidade de telefonia corporativa.</span><span class="sxs-lookup"><span data-stu-id="872c3-146">Offers enterprise telephony functionality.</span></span>


![Ícone do Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="872c3-148">Aproveitado para sites e portais (ex.: notícias e anúncios de empresas, pesquisa e colaboração de documentos).</span><span class="sxs-lookup"><span data-stu-id="872c3-148">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="872c3-149">Implementa a automação de processos comerciais em bibliotecas de documentos e listas de informações, integrando o Microsoft Flow e o PowerApps.</span><span class="sxs-lookup"><span data-stu-id="872c3-149">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="872c3-150">O site SharePoint da equipe totalmente alimentado é provisionado para cada equipe do Microsoft Teams para armazenamento de arquivos, notícias da equipe, páginas, listas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="872c3-150">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="872c3-151">Consulte [Como o SharePoint Online e o OneDrive for Business interagem com o Teams](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="872c3-151">[How SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="872c3-152">O que aconteceu com as Perguntas Frequentes do Administrador do Teams?</span><span class="sxs-lookup"><span data-stu-id="872c3-152">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="872c3-153">Apesar de as Perguntas Frequentes do Administrador do Teams estarem acessíveis quando lançamos o Teams, rapidamente elas se tornaram uma “sopa de letrinhas”, sendo difícil de encontrar qualquer coisa específica.</span><span class="sxs-lookup"><span data-stu-id="872c3-153">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="872c3-154">Assim, encerramos as Perguntas Frequentes e incorporamos suas valiosas informações na documentação de Teams que você vê agora.</span><span class="sxs-lookup"><span data-stu-id="872c3-154">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="872c3-155">Você encontrará em contexto nesta documentação todas as informações que estavam nas Perguntas Frequentes.</span><span class="sxs-lookup"><span data-stu-id="872c3-155">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="872c3-156">Se estiver procurando alguma coisa e não encontra aqui, informe-nos na seção de **Comentários**.</span><span class="sxs-lookup"><span data-stu-id="872c3-156">If you're looking for something that you can't find here, please tell us about it in the **Comments** section below.</span></span> <span data-ttu-id="872c3-157">Tentaremos responder aos seus comentários dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="872c3-157">We try to respond to your comments within 24 hours.</span></span>

<span data-ttu-id="872c3-158">A propósito, nós ainda **temos** uma seção de Perguntas Frequentes para a [Jornada de migração do Skype for Business para o Microsoft Teams](FAQ-journey.md).</span><span class="sxs-lookup"><span data-stu-id="872c3-158">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 