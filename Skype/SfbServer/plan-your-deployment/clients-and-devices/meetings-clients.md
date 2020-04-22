---
title: Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumo: os profissionais de ti devem analisar os requisitos de suporte para o aplicativo do Skype for Business Web App e reuniões do Skype durante o planejamento do Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.'
ms.openlocfilehash: 0e1ce225f99a112f11d55d76eb8039a10d9aac6b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777786"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)
 
**Resumo:** Os profissionais de ti devem analisar os requisitos de suporte para o aplicativo do Skype for Business Web App e reuniões do Skype durante o planejamento do Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.
  
Depois de implementar o Skype for Business Server, os usuários da sua organização terão presumivelmente o cliente Skype for Business instalado como parte do processo de implantação. 
  
Mais tarde, esses usuários podem criar reuniões e convidar usuários de fora da organização, e os convidados da reunião podem não ter qualquer versão do cliente Skype for Business. Quando os usuários clicarem na URL para o convite da reunião, a ausência de um cliente será detectada e o convidado sem um cliente do Skype for Business será solicitado a baixar e instalar um cliente leve e apenas reuniões para que eles possam participar da reunião.
  
> [!NOTE]
> O aplicativo Skype for Business Web App e reuniões do Skype só estão disponíveis ao tentar fazer logon em uma reunião sem ter o Skype for Business. A ajuda do usuário para esses aplicativos [https://aka.ms/smahelp](https://aka.ms/smahelp)é em. 
  
> [!NOTE]
> Não é possível pré-instalar o aplicativo Skype for Business Web App ou Skype reuniões, mas os usuários de [telefone inteligente](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) podem ser capazes de instalar clientes móveis de baixo custo que eles podem usar para participar de reuniões.
  
Por padrão, o servidor que hospeda a reunião orientará o usuário a baixar e instalar o Skype for Business Web App para ingressar na reunião. O Skype for Business Web App é armazenado no servidor front-end e é enviado para o participante da reunião. 
  
Para o Skype for Business Server, o aplicativo reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) estão disponíveis como substituições para o Skype for Business Web App, começando com o CU5, mas fornecer os aplicativos de substituição requer a configuração adicional descrita em [habilitar o aplicativo de reuniões do Skype para substituir o Skype for Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Se o aplicativo reuniões do Skype e o Skype for Business para Mac estiverem habilitados, os usuários baixarão a versão mais recente dos aplicativos da CDN (rede de distribuição de conteúdo) do Office 365, em vez do Skype for Business Server. Para o Skype for Business Server 2019, usar o aplicativo reuniões do Skype e o Skype for Business para Mac é a única opção.
  
O aplicativo reuniões do Skype oferece uma experiência de navegador simplificada para baixar e instalar o aplicativo e ingressar em reuniões, incluindo o ingresso de um clique para usuários do Internet Explorer. O aplicativo de reuniões do Skype também tem vários aprimoramentos sobre o Skype for Business Web App para confiabilidade e a experiência da reunião. 
  
> [!NOTE]
> A partir do Skype for Business Server 2015 CU5 ou posterior, as reuniões mantidas usando o Skype for Business online não enviarão mais um usuário sem cliente do Skype for Business Web App, em vez disso, serão enviadas aplicativos de reuniões do Skype (no Windows) ou Skype for Business para Mac (no Mac). A partir do Skype for Business Server 2015 CU5 ou posterior, se você [habilitar o aplicativo reuniões do Skype para substituir o Skype for Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), os usuários do cliente serão enviados aplicativo de reuniões do Skype ou Skype for Business para Mac, e não Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar o Skype for Business Web App, um usuário deve ter uma das seguintes combinações de sistema operacional e navegador com suporte. 
  
**Sistema operacional e suporte mínimo de navegador para o Skype for Business Web App**

| Sistema operacional | Borda | Internet Explorer 11 de 32 e 64 bits ou posterior | Internet Explorer 10 de 32 e 64 bits ou posterior | Internet Explorer 9 de 32 e 64 bits ou posterior | Versão de 32 e 64 bits do Safari 6.2.8-11. X | Versão de 32 e 64 bits do Chrome 18. X ou posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |Não disponível  <br/> |Não disponível  <br/> |Sim &#x2778; <br/> |
|Windows 8,1 &#x2776; <br/> |N/D  <br/> |Sim  <br/> |N/D  <br/> |Não disponível  <br/> |Não disponível <br/> |Sim &#x2778; <br/> |
|&#x2776; Windows 8 (baseado em Intel) <br/> |Não disponível  <br/> |Não disponível  <br/> |Sim  <br/> |N/D <br/> |Não disponível  <br/> |Sim &#x2778; <br/> |
|Windows 7 com SP1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |N/D <br/>|Sim &#x2778; <br/> |
|Windows Server 2008 R2 com SP1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |N/D <br/>|Sim &#x2778; <br/> |
|macOS 10,8 e posterior (baseado em Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Não disponível  <br/> |Sim  <br/> |Sim <br/> |
   
&#x2776; o plug-in do navegador do Skype for Business Web App requer um plug-in de compartilhamento específico para usar voz, vídeo, compartilhamento e exibição de compartilhamento contínuo de tela e outros recursos baseados no computador. Um participante de reunião recebe a opção de instalar o plug-in de compartilhamento ao ingressar na reunião ou ao iniciar um desses recursos. No Windows 8 e Windows 8,1, o plug-in de compartilhamento pode ser instalado somente se você estiver executando o Internet Explorer 10 ou o Internet Explorer 11 para a área de trabalho. Esses recursos não estão disponíveis em versões que não sejam de área de trabalho do Internet Explorer 10 e 11. Observe que o Firefox e o Safari versão 12,0 e posterior não são mais suportados.
  
&#x2777; nos sistemas operacionais Windows 7, Windows Server 2008 R2 e Macintosh com suporte, todos os recursos estão disponíveis, incluindo voz, vídeo, visualização de aplicativos, compartilhamento de aplicativos, visualização de área de trabalho e compartilhamento de área de trabalho baseados no computador. Para usar esses recursos, você deve instalar um plug-in quando solicitado. Observe que o Mac OS X versão 10,7 não é mais suportado.  Observe também que o aplicativo Web não será instalado no OS X 10,15 ou posterior.  Recomendamos usar a versão mais recente do Skype for Business para Mac, que oferece suporte a cenários de junção anônimas em frente.
  
&#x2778; acessar o aplicativo Web do Chrome no Windows iniciará um pequeno programa que carrega o aplicativo Web em um quadro do Internet Explorer incorporado. Este programa requer que uma das versões suportadas do Internet Explorer esteja instalada para que o aplicativo Web seja carregado corretamente.
  
> [!NOTE]
> Os usuários do Microsoft 365 e do Office 365 podem usar o Internet Explorer 10 ou posterior com o Skype for Business. 
  
### <a name="skype-meetings-app"></a>Aplicativo de Reuniões do Skype

O aplicativo de reuniões do Skype é executado como um aplicativo em computadores que usam o Windows 10, Windows 8,1, Windows 8, Windows 7, com 32 e 64-bit Internet Explorer 11 ou posterior instalado. 
  
Para qualquer outra dependência, consulte [plataformas com suporte para o aplicativo de reuniões do Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business para Mac

O Skype for Business para Mac é executado em computadores usando o macOS versão 10,8 ou posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Os requisitos de hardware do computador são determinados pelo navegador e pelo sistema operacional. Os recursos de voz e telefonia exigem um microfone e alto-falantes, headset com microfone ou dispositivo equivalente compatível com o computador. Os recursos de vídeo exigem um dispositivo de vídeo compatível com o computador. Para obter informações detalhadas sobre suporte de hardware de vídeo e qualidade de vídeo esperada, consulte informações sobre as [resoluções de vídeo do cliente Skype for Business](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de rede
<a name="Network"> </a>

Se um usuário do Skype for Business Web App ou do aplicativo de reuniões do Skype estiver enfrentando problemas de conexão de reunião, a infraestrutura de rede da sua organização não é configurada para dar suporte ao Office 365, conforme descrito em [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esse é o caso de a reunião ter sido criada por um usuário do Skype for Business online ou do Skype for Business Server. 
  
Se o usuário estiver em uma rede não configurada conforme descrito, muitos recursos do aplicativo podem ou não funcionar e talvez não consigam se conectar à reunião.
  
## <a name="supported-meetings-features"></a>Recursos de reuniões com suporte
<a name="BKMK_Conferencing"> </a>

Esta tabela compara os recursos de reuniões disponíveis para os usuários do cliente Skype for Business, Skype for Business Web App, aplicativo de reuniões do Skype e Lync Web App. O Lync Web App está listado para fins de comparação de recursos: um usuário só baixaria e usaria o Lync Web App se a reunião estivesse hospedada em um servidor Lync 2013.

| Recurso/capacidade | Cliente do Skype for Business 2016 ou 2019 | Skype for Business no cliente Mac | Aplicativo de Reuniões do Skype | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicione áudio de computador  <br/> |&#x2714;|&#x2714;|&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |
|Adicione vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |
|Alternar áudio para um telefone para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alternar áudio para um telefone para participantes convidados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Exibir vídeo de vários participantes (modo de exibição de galeria)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhamento de tela baseado em vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (somente exibição)  <br/> |||
|Use controles de apresentador durante a reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acesse a lista da reunião detalhada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de IM com várias partes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Definir mensagens INSTANTÂNEAs como alta prioridade  <br/> |&#x2714;|||||
|Compartilhe a área de trabalho (se ativado)  <br/> |&#x2714;|&#x2714;|&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |&#x2714; (exige plug-in)  <br/> |
|Compartilhe um programa (se ativado)  <br/> |&#x2714;||&#x2714; (somente no Windows; requer plug-in)  <br/> |&#x2714; (somente no Windows; requer plug-in)  <br/> |&#x2714; (somente no Windows; requer plug-in)  <br/> |
|Assumir o controle da área de trabalho ou do programa compartilhado de outro usuário  <br/> |&#x2714;||&#x2714; (&#x2776; somente no Windows; requer plug-in)  <br/> |&#x2714; (&#x2776; somente no Windows; requer plug-in)  <br/> |&#x2714; (&#x2776; somente no Windows; requer plug-in)  <br/> |
|Permitir que outro usuário assuma o controle de sua área de trabalho ou programa compartilhado  <br/> |&#x2714;|||||
|Adicione participantes anônimos (se ativado)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes por nome  <br/> |&#x2714;|&#x2714;||||
|Convidar participantes por número de telefone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes por email  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniões de áudio discada  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar uma reunião agora  <br/> |&#x2714;|&#x2714;||||
|Gravar uma reunião  <br/> |&#x2714;|||||
|Adicionar e baixar anexos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Adicione e apresente arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicionar e editar anotações de reunião do OneNote  <br/> |&#x2714;||Somente edição (não adicionar)  <br/> |Somente edição (não adicionar)  <br/> |Somente edição (não adicionar)  <br/> |
|Use um quadro de avisos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Faça votações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Carregar arquivos para compartilhar com outras pessoas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programe uma reunião ou conferência  <br/> |Agendador da Web do Outlook ou Skype for Business  <br/> |Agendador da Web do Outlook ou Skype for Business  <br/> |Agendador da Web do Skype for Business  <br/> |Agendador da Web do Skype for Business  <br/> |Agendador da Web do Skype for Business  <br/> |
|P&amp;um gerente  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Desabilitar vídeo de participante  <br/> |&#x2714;|||||
|Desabilitar IM de reunião  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Audiência sem áudio  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Tornar todos um participante  <br/> |&#x2714;|||||
|Produzir transmissão de reunião do Skype  <br/> |&#x2714;|||||
   
 &#x2776; participantes não podem controlar áreas de trabalho compartilhadas pelos usuários do Skype for Mac, Lync para Mac 2011 ou Communicator para Mac 2011. Isso também não funciona para o Skype for Business Web App no máximo OSX.
  
 &#x2777; para o Skype for Business Online, esse recurso exige conferências PSTN da Microsoft, Unificação de mensagens do Exchange ou um provedor de audioconferência de terceiros.
  
 &#x2778; o cliente do Lync para Mac 2011 não pode exibir apresentações do PowerPoint do Microsoft Office 2013 quando elas tiverem sido compartilhadas em uma conferência pelo Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conhecidos e solução de problemas
<a name="BKMK_Conferencing"> </a>

Para os usuários finais, a [ajuda online](https://aka.ms/smahelp) desses aplicativos está prontamente disponível. Os profissionais de ti devem estar cientes dos seguintes problemas:
  
- Se o usuário estiver em uma rede não configurada para atender aos [requisitos de rede](meetings-clients.md#Network), muitos recursos do aplicativo poderão ou não funcionar, e talvez não consigam se conectar à reunião.
    
- Alguns usuários podem ter computadores administrados pela empresa com permissão desabilitada para instalar aplicativos. para esses usuários, nenhum aplicativo é uma opção, mas os usuários de [telefone inteligente](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) podem conseguir instalar clientes móveis de baixo custo que eles podem usar para participar de reuniões.
    
    Outros problemas de instalação também são abordados nos [Tópicos da ajuda](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Os usuários podem ver um aviso de firewall na primeira vez que executam o aplicativo reuniões. Eles podem ser solicitados a abrir portas para otimizar a experiência, e isso pode exigir privilégios de administrador no computador que eles podem não ter. O aplicativo ainda deve funcionar e o usuário pode recusar com segurança para abrir as portas solicitadas. 
    
- Você deve ter o [ActiveX habilitado sem filtragem](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) no Internet Explorer, mesmo que o IE não seja seu navegador padrão. No Skype for Business Web App, um controle ActiveX — um módulo pequeno que adiciona recursos adicionais a um aplicativo Web ou outro programa — é necessário para compartilhamento de áudio, vídeo e tela.
    
- Para que alguns recursos do Skype for Business Web App funcionem corretamente, você deve permitir que seu navegador [salve cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) no seu computador ou dispositivo.
    
- Talvez seja necessário ativar o suporte a [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) no navegador para que alguns recursos do Skype for Business Web App funcionem conforme o esperado.
    
### <a name="aes-support"></a>Suporte AES 

A partir do Skype for Business Server 2015 CU5, não há suporte para AES para o ASP.NET 4,6, e isso pode fazer com que o aplicativo de reuniões do Skype falhe ao iniciar. [Os requisitos de criptografia devido ao ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) têm mais detalhes.
  
## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Implantar clientes para download da Web no Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo de reuniões do Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
