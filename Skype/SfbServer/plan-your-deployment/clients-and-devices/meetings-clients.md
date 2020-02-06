---
title: Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)
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
description: 'Resumo: os profissionais de ti devem analisar os requisitos de suporte para o aplicativo Skype for Business Web App e reuniões do Skype durante o planejamento para o Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.'
ms.openlocfilehash: 126d8ffc71a2ff1a0bcbf26c744301736d2b47b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803551"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)
 
**Resumo:** Os profissionais de ti devem analisar os requisitos de suporte para o aplicativo Skype for Business Web App e reuniões do Skype durante o planejamento para o Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.
  
Depois de implementar o Skype for Business Server, o cliente da sua organização terá, presumidamente, o cliente Skype for Business instalado como parte do processo de implantação. 
  
Mais tarde, esses usuários podem criar reuniões e convidar usuários de fora da organização, e esses convidados podem não ter qualquer versão do cliente Skype for Business. Quando esses usuários clicam na URL para o convite da reunião, a falta de um cliente será detectada e o convidado sem um cliente Skype for Business será solicitado a baixar e instalar um cliente leve e somente reuniões para que ele possa ingressar na reunião.
  
> [!NOTE]
> O aplicativo Skype for Business Web App e reuniões do Skype só estão disponíveis quando você tenta se conectar a uma reunião sem ter o Skype for Business. A ajuda do usuário para esses aplicativos [https://aka.ms/smahelp](https://aka.ms/smahelp)está em. 
  
> [!NOTE]
> Você não pode pré-instalar o aplicativo Skype for Business Web App ou reuniões do Skype, mas os usuários do [telefone inteligente](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e do [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podem ser capazes de instalar clientes móveis de baixo custo que eles podem usar para participar de reuniões.
  
Por padrão, o servidor que hospeda a reunião direcionará o usuário para baixar e instalar o Skype for Business Web App para ingressar na reunião. O Skype for Business Web App está armazenado no servidor front-end e é enviado ao participante da reunião. 
  
Para o Skype for Business Server, o aplicativo reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) estão disponíveis como substituições para o Skype for Business Web App, começando com o CU5, mas o fornecimento dos aplicativos de substituição requer a configuração adicional descrita em [habilitar o aplicativo reuniões do Skype para substituir o Skype for Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Se o aplicativo reuniões do Skype e o Skype for Business para Mac estiverem habilitados, os usuários baixarão a versão mais recente dos aplicativos da CDN (rede de distribuição de conteúdo) do Office 365 em vez de usar o Skype for Business Server. Para o Skype for Business Server 2019, usar o aplicativo reuniões do Skype e o Skype for Business para Mac é a única opção.
  
O aplicativo reuniões do Skype oferece uma experiência de navegador simplificada para baixar e instalar o aplicativo e ingressar em reuniões, incluindo ingressar em um clique para usuários do Internet Explorer. O aplicativo reuniões do Skype também tem vários aprimoramentos com o Skype for Business Web App para confiabilidade e a experiência da reunião. 
  
> [!NOTE]
> A partir do Skype for Business Server 2015 CU5 ou posterior, as reuniões mantidas usando o Skype for Business online não enviarão mais um usuário sem clientes para o Skype for Business Web App, em vez disso, serão enviadas o aplicativo reuniões do Skype (no Windows) ou o Skype for Business para Mac (no Mac). A partir do Skype for Business Server 2015 CU5 ou posterior, se você [habilitar o aplicativo reuniões do Skype para substituir o Skype for Business Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), os usuários sem cliente serão enviados aplicativo reuniões do Skype ou o Skype for Business para Mac, e não o Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar o Skype for Business Web App, um usuário deve ter uma das seguintes combinações de sistema operacional e navegador compatíveis. 
  
**Sistema operacional e suporte mínimo ao navegador para o Skype for Business Web App**

| Sistema operacional | Borda | Internet Explorer 11 de 32 e 64 bits ou posterior | Internet Explorer 10 de 32 e 64 bits ou posterior | 32-e o Internet Explorer 9 de 64 bits ou posterior | Versão de 32 a 64 bits do Safari 6.2.8-11. X | Versão de 32 a 64 bits do Chrome 18. X ou posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sim &#x2778; <br/> |
|&#x2776; do Windows 8,1 <br/> |N/D  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sim &#x2778; <br/> |
|&#x2776; Windows 8 (baseado na Intel) <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |N/D <br/> |N/D  <br/> |Sim &#x2778; <br/> |
|Windows 7 com SP1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |Não disponível <br/>|Sim &#x2778; <br/> |
|Windows Server 2008 R2 com SP1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |N/D <br/>|Sim &#x2778; <br/> |
|&#x2777; macOS 10,8 e posteriores (baseados em Intel) <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |Sim <br/> |
   
&#x2776; plug-in do navegador do Skype for Business Web App exige um plug-in de compartilhamento específico para usar voz, vídeo, compartilhamento e exibição de compartilhamento contínuo de tela e outros recursos baseados em computador. Um participante da reunião recebe a opção para instalar o plug-in de compartilhamento quando ele ingressa na reunião ou quando ele inicia um desses recursos. No Windows 8 e no Windows 8,1, o plug-in de compartilhamento pode ser instalado apenas se você estiver executando o Internet Explorer 10 ou o Internet Explorer 11 para a área de trabalho. Esses recursos não estão disponíveis para versões não relacionadas à área de trabalho do Internet Explorer 10 e 11. Observe que o Firefox e o Safari versão 12,0 e posterior não são mais suportados.
  
&#x2777; em sistemas operacionais Windows 7, Windows Server 2008 R2 e Macintosh compatíveis, todos os recursos estão disponíveis, incluindo voz baseada em computador, vídeo, visualização de aplicativos, compartilhamento de aplicativos, exibição na área de trabalho e compartilhamento de área de trabalho. Para usar esses recursos, é preciso instalar o plug-in assim que for solicitado. Observe que não há mais suporte para a versão 10.7 do Mac OS X.
  
&#x2778; acessar o aplicativo Web do Chrome no Windows iniciará um pequeno programa que carrega o aplicativo Web em um quadro do Internet Explorer inserido. Esse programa requer que uma das versões com suporte do Internet Explorer esteja instalada para que o aplicativo Web seja carregado corretamente.
  
> [!NOTE]
> Os usuários do Office 365 podem usar o Internet Explorer 10 ou posterior com o Skype for Business. 
  
### <a name="skype-meetings-app"></a>Aplicativo Reuniões do Skype

O aplicativo reuniões do Skype é executado como um aplicativo em computadores que usam o Windows 10, o Windows 8,1, o Windows 8, o Windows 7, com o 32 e o 64-bit Internet Explorer 11 ou posterior instalado. 
  
Para qualquer outra dependência, consulte [plataformas com suporte para o aplicativo reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business para Mac

O Skype for Business para Mac é executado em computadores que usam o macOS versão 10,8 ou posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Os requisitos de hardware são determinados pelo sistema operacional e pelo navegador. Os recursos de voz e de telefonia exigem um microfone e alto-falantes, fone de ouvido com microfone ou dispositivo equivalente compatível com o computador. Os recursos de vídeo exigem um dispositivo de vídeo compatível com o computador. Para obter informações detalhadas sobre o suporte de hardware de vídeo e a qualidade de vídeo esperada, consulte [resoluções de vídeo do cliente Skype for Business](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de rede
<a name="Network"> </a>

Se um usuário do aplicativo Skype for Business Web App ou reuniões do Skype enfrentar problemas de conexão de reunião, provavelmente a infraestrutura de rede de sua organização não está configurada para dar suporte ao Office 365 conforme descrito nas [URLs e intervalos de endereços IP do office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esse é o caso de a reunião ter sido criada por um usuário do Skype for Business online ou do Skype for Business Server. 
  
Se o usuário estiver em uma rede não configurada conforme descrito, muitos recursos de aplicativo podem ou não funcionar e talvez não consigam se conectar à reunião.
  
## <a name="supported-meetings-features"></a>Recursos de Reuniões com suporte
<a name="BKMK_Conferencing"> </a>

Esta tabela compara os recursos de reuniões disponíveis para usuários do cliente Skype for Business, Skype for Business Web App, aplicativo reuniões do Skype e Lync Web App. O Lync Web App está listado para fins de comparação de recursos: um usuário só baixaria e usará o Lync Web App se a reunião estivesse hospedada em um servidor do Lync 2013.

| Recurso/funcionalidade | Cliente do Skype for Business 2016 ou 2019 | Cliente Skype for Business no Mac | Aplicativo Reuniões do Skype | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicionar áudio do computador  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Adicionar vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Alternar o áudio para um telefone para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alternar o áudio para um telefone para participantes convidados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhamento de tela baseado em vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (somente exibição)  <br/> |||
|Usar os controles do apresentador na reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acessar a lista de participantes detalhada da reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participar de IM com vários participantes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Definir mensagens instantâneas com alta prioridade  <br/> |&#x2714;|||||
|Compartilhar a área de trabalho (se habilitado)  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Compartilhar um programa (se habilitado)  <br/> |&#x2714;||&#x2714; (somente no Windows; requer plug-in)  <br/> |&#x2714; (somente no Windows; requer plug-in)  <br/> |&#x2714; (somente no Windows; requer plug-in)  <br/> |
|Assuma o controle da área de trabalho ou do programa compartilhado de outro usuário  <br/> |&#x2714;||&#x2714; (&#x2776; somente no Windows; exige plug-in)  <br/> |&#x2714; (&#x2776; somente no Windows; exige plug-in)  <br/> |&#x2714; (&#x2776; somente no Windows; exige plug-in)  <br/> |
|Permitir que outro usuário assuma o controle da sua área de trabalho ou programa compartilhado  <br/> |&#x2714;|||||
|Adicionar participantes anônimos (se habilitado)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes por nome  <br/> |&#x2714;|&#x2714;||||
|Convidar participantes por número de telefone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes por email  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniões de áudio discadas  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar uma reunião do tipo Reunir Agora  <br/> |&#x2714;|&#x2714;||||
|Gravar uma reunião  <br/> |&#x2714;|||||
|Adicionar e baixar anexos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Adicionar e apresentar arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar por arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar e editar notas de reunião do OneNote  <br/> |&#x2714;||Somente editar (sem adicionar)  <br/> |Somente editar (sem adicionar)  <br/> |Somente editar (sem adicionar)  <br/> |
|Usar um quadro de comunicações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar votações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Carregar arquivos para compartilhar com outras pessoas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Agendar um reunião ou conferência  <br/> |Agendador do Outlook ou Skype for Business Web  <br/> |Agendador do Outlook ou Skype for Business Web  <br/> |Agendador da Web do Skype for Business  <br/> |Agendador da Web do Skype for Business  <br/> |Agendador da Web do Skype for Business  <br/> |
|P&amp;um gerente  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Desabilitar vídeo de participante  <br/> |&#x2714;|||||
|Desabilitar mensagens instantâneas de reunião  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Ativar mudo do público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Tornar todos participantes  <br/> |&#x2714;|||||
|Produzir Transmissão de Reunião do Skype  <br/> |&#x2714;|||||
   
 &#x2776; participantes não podem controlar áreas de trabalho que são compartilhadas pelos usuários do Skype for Business para Mac, Lync para Mac 2011 ou Communicator para Mac 2011. Isso também não funcionará para o Skype for Business Web App no máximo OSX.
  
 &#x2777; para o Skype for Business Online, esse recurso requer a conferência PSTN da Microsoft, a Unificação de mensagens do Exchange ou um provedor de serviços de audioconferência de terceiros.
  
 &#x2778; o cliente do Lync for Mac 2011 não pode exibir apresentações do PowerPoint do Microsoft Office 2013 quando foram compartilhados em uma conferência pelo Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conhecidos e solução de problemas
<a name="BKMK_Conferencing"> </a>

Para usuários finais, a [ajuda online](https://aka.ms/smahelp) para esses aplicativos está prontamente disponível. Os profissionais de ti devem estar cientes dos seguintes problemas:
  
- Se o usuário estiver em uma rede não configurada para atender aos [requisitos de rede](meetings-clients.md#Network), muitos recursos do aplicativo poderão ou não funcionar e talvez não consigam se conectar à reunião.
    
- Alguns usuários podem ter computadores administrados pela empresa com permissão desabilitada para instalar aplicativos. para esses usuários, nenhum aplicativo é uma opção, mas os usuários do [telefone inteligente](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e do [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podem ser capazes de instalar clientes móveis baratos que podem usar para participar de reuniões.
    
    Outros problemas de instalação também são abordados nos [Tópicos da ajuda](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Os usuários podem ver um aviso de firewall na primeira vez que executarem o aplicativo reuniões. Eles podem ser solicitados a abrir as portas para otimizar a experiência, e isso pode exigir privilégios de administrador na máquina que elas podem não ter. O aplicativo ainda deve funcionar e o usuário pode recusar com segurança para abrir as portas solicitadas. 
    
- Você deve ter o [ActiveX habilitado sem filtragem](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) no Internet Explorer, mesmo que o IE não seja o navegador padrão. No Skype for Business Web App, um controle ActiveX — um pequeno módulo que adiciona mais recursos a um aplicativo Web ou outro programa — é necessário para compartilhamento de áudio, vídeo e tela.
    
- Para que alguns recursos do Skype for Business Web App funcionem corretamente, você deve permitir que o navegador [salve cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) em seu computador ou dispositivo.
    
- Talvez seja necessário ativar o suporte de [JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) em seu navegador para que alguns recursos do Skype for Business Web App funcionem conforme o esperado.
    
### <a name="aes-support"></a>Suporte para AES 

A partir do Skype for Business Server 2015 CU5, o AES não é compatível com o ASP.NET 4,6, e isso pode fazer com que o aplicativo reuniões do Skype falhe ao iniciar. [Os requisitos de criptografia devido ao ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) têm mais detalhes.
  
## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Implantar clientes para download da Web no Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
