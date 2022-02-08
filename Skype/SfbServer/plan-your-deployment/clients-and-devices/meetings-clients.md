---
title: Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumo: os profissionais de TI devem revisar os requisitos de suporte para o aplicativo de reuniões Skype for Business Web App e Skype durante o planejamento de Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.'
ms.openlocfilehash: bf6eb62291309500c942e83c41e898b5a4d25531
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395153"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)
 
**Resumo:** Os profissionais de TI devem revisar os requisitos de suporte para o aplicativo de reuniões Skype for Business Web App e Skype durante o planejamento de Skype for Business Server. Este artigo não se destina aos usuários desses aplicativos.
  
Depois de implementar o Skype for Business Server, os usuários da sua organização provavelmente terão o cliente Skype for Business instalado como parte do processo de implantação. 
  
Posteriormente, esses usuários podem criar reuniões e convidar usuários de fora da organização, e esses convidados de reunião podem não ter nenhuma versão do cliente Skype for Business. Quando esses usuários clicam na URL do convite da reunião, a falta de um cliente será detectada e o convidado sem um cliente Skype for Business será solicitado a baixar e instalar um cliente leve, somente reuniões, para que eles possam ingressar na reunião.
  
> [!NOTE]
> O Skype for Business Web App e o Skype reuniões estão disponíveis apenas ao tentar fazer logoff em uma reunião sem Skype for Business. A ajuda do usuário para esses aplicativos está em [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Não é possível pré-instalar o aplicativo de reuniões Skype for Business Web App ou Skype, mas os usuários de smartphones [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [tablets](https://products.office.com/skype-for-business/download-app?tab=tabs-2) podem instalar clientes móveis baratos que podem usar para participar de reuniões.
  
Por padrão, o servidor que hospeda a reunião direcionará o usuário para baixar e instalar Skype for Business Web App participar da reunião. O Skype for Business Web App é armazenado no Servidor Front-End e é enviado para o participante da reunião. 
  
Para Skype for Business Server, o Skype meetings (no Windows) e o Skype for Business para Mac (no Mac) estão disponíveis como substituições para Skype for Business Web App  começando com o CU5, mas fornecer os aplicativos de substituição requer a configuração adicional descrita em [Enable Skype Meetings App para substituir Skype for Business Web App (Opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Se Skype de reuniões e Skype for Business para Mac estão habilitados, os usuários baixarão a versão mais recente dos aplicativos do Microsoft 365 ou Office 365 Rede de Distribuição de Conteúdo (CDN) em vez disso do que do seu Skype for Business servidor. Para Skype for Business Server 2019, usar o Skype Meetings App e Skype for Business para Mac é a única opção.
  
Skype Meetings App oferece uma experiência de navegador simplificada para baixar e instalar o aplicativo e participar de reuniões, incluindo a junção de um clique para usuários do Internet Explorer. Skype Meetings App também tem muitas melhorias sobre o Skype for Business Web App para confiabilidade e a experiência de reunião. 
  
> [!NOTE]
> A partir de Skype for Business Server 2015 CU5 ou posterior, as reuniões realizadas usando o Skype for Business Online não enviarão mais o Skype for Business Web App a um usuário sem cliente, em vez disso, serão enviadas Skype Meetings App (no Windows) ou Skype for Business para Mac (no Mac). A partir de Skype for Business Server 2015 CU5 ou posterior, se você habilitar o aplicativo de reuniões do Skype para substituir o [Skype for Business Web App (Opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), os usuários sem cliente serão enviados Skype Aplicativo de Reuniões ou Skype for Business para Mac em vez de Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisitos de software
<a name="OS-Browser"> </a>

Para usar o Skype for Business Web App, um usuário deve ter uma das seguintes combinações de sistema operacional e navegador com suporte. 
  
**Sistema operacional e suporte mínimo ao navegador para Skype for Business Web App**

| Sistema operacional | Borda | Internet Explorer 11 ou posterior de 32 e 64 bits | 32 e 64 bits Internet Explorer 10 ou posterior | Internet Explorer 9 ou posterior de 32 e 64 bits | Versão de 32 e 64 bits do Safari 6.2.8 - 11.X | Versão de 32 e 64 bits do Chrome 18.X ou posterior |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sim &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/D  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sim &#x2778; <br/> |
|Windows 8 (baseado em Intel) &#x2776; <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |N/D <br/> |N/D  <br/> |Sim &#x2778; <br/> |
|Windows 7 com sp1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |N/D <br/>|Sim &#x2778; <br/> |
|Windows Server 2008 R2 com sp1 &#x2777; <br/> |N/D  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |N/D <br/>|Sim &#x2778; <br/> |
|macOS 10.8 e posterior (baseado em Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |Sim <br/> |
   
&#x2776; O plug-in do navegador Skype for Business Web App requer um plug-in de compartilhamento específico para usar voz, vídeo, compartilhamento e exibição de compartilhamento de tela em andamento e outros recursos. Um participante de reunião recebe a opção de instalar o plug-in de compartilhamento quando ingressar na reunião ou quando inicia um desses recursos. No Windows 8 e Windows 8.1, o plug-in de compartilhamento só poderá ser instalado se você estiver executando o Internet Explorer 10 ou o Internet Explorer 11 para a área de trabalho. Esses recursos não estão disponíveis com versões não desktop de Internet Explorer 10 e 11. Observe que o Firefox e o Safari versão 12.0 e posteriores não são mais suportados.
  
&#x2777; On com suporte Windows 7, sistemas operacionais do Windows Server 2008 R2 e Macintosh, todos os recursos estão disponíveis, incluindo voz, vídeo, exibição de aplicativos, compartilhamento de aplicativos, exibição de área de trabalho e compartilhamento de área de trabalho. Para usar esses recursos, você deve instalar um plug-in quando solicitado. Observe que o Mac OS X versão 10.7 não é mais suportado.  Observe também que o aplicativo Web não será instalado no SISTEMA OPERACIONAL X 10.15 ou posterior.  Recomendamos usar a versão mais recente do Skype for Business para Mac que oferece suporte a cenários de junção anônimos em frente.
  
&#x2778; acessar o Aplicativo Web do Chrome no Windows iniciará um pequeno programa que carrega o Aplicativo Web em um quadro incorporado do Internet Explorer. Este programa exige que uma das versões com suporte do Internet Explorer seja instalada para que o Aplicativo Web seja carregado corretamente.
  
> [!NOTE]
> Microsoft 365 e Office 365 usuários podem usar Internet Explorer 10 ou posterior com Skype for Business. 
  
### <a name="skype-meetings-app"></a>Aplicativo de Reuniões do Skype

Skype Meetings App é executado como um aplicativo em computadores usando Windows 10, Windows 8.1, Windows 8, Windows 7, com o Internet Explorer 11 de 32 e 64 bits ou posterior instalado. 
  
Para outras dependências, consulte Plataformas com suporte para [o Skype Meetings App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business para Mac

Skype for Business para Mac em computadores que usam macOS versão 10.8 ou posterior. 

## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Os requisitos de hardware do computador são determinados pelo sistema operacional e pelo navegador. Os recursos de voz e telefonia exigem microfone e alto-falantes, fone de ouvido com microfone ou dispositivo equivalente compatível com o computador. Os recursos de vídeo exigem um dispositivo de vídeo compatível com o computador. Para obter informações detalhadas sobre o suporte ao hardware de vídeo e a qualidade de vídeo esperada, [consulte Skype for Business de vídeo cliente](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de rede
<a name="Network"> </a>

Se um usuário do Skype for Business Web App ou do Skype Meetings App tiver problemas de conexão de reunião, as chances são de que a infraestrutura de rede da organização não seja configurada para dar suporte Office 365 como descrito em [urls Office 365 e intervalos de endereços IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esse é o caso se a reunião foi criada por um usuário do Skype for Business Online ou Skype for Business Server. 
  
Se o usuário estiver em uma rede não configurada conforme descrito, muitos recursos do aplicativo poderão ou não funcionar e talvez não possam se conectar à reunião.
  
## <a name="supported-meetings-features"></a>Recursos de reuniões com suporte
<a name="BKMK_Conferencing"> </a>

Esta tabela compara os recursos de Reuniões disponíveis aos usuários do cliente Skype for Business, Skype for Business Web App, Skype Reuniões e Lync Web App. O Lync Web App está listado para fins de comparação de recursos: um usuário só estaria baixando e usando o Lync Web App se a reunião fosse hospedada em um servidor do Lync 2013.

| Recurso/funcionalidade | Skype for Business cliente 2016 ou 2019 | Skype for Business no cliente Mac | Aplicativo de Reuniões do Skype | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicione áudio de computador  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Adicione vídeo  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Alternar áudio para um telefone para participantes autenticados  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Alternar áudio para um telefone para participantes convidados  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Exibir vídeo de várias partes (modo de exibição de galeria)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhamento de tela baseado em vídeo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(Somente exibição)  <br/> |||
|Use controles de apresentador durante a reunião  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Acesse a lista da reunião detalhada  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participe de IM com várias partes  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Definir mensagens de mensagens IM como de alta importância  <br/> |&#x2714;|||||
|Compartilhe a área de trabalho (se ativado)  <br/> |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |&#x2714; (requer plug-in)  <br/> |
|Compartilhe um programa (se ativado)  <br/> |&#x2714;||&#x2714;(Somente Windows, requer plug-in)  <br/> |&#x2714;(Somente Windows, requer plug-in)  <br/> |&#x2714;(Somente Windows, requer plug-in)  <br/> |
|Assumir o controle da área de trabalho ou programa compartilhado de outro usuário  <br/> |&#x2714;||&#x2714; (&#x2776; on Windows somente; requer plug-in)  <br/> |&#x2714; (&#x2776; on Windows somente; requer plug-in)  <br/> |&#x2714; (&#x2776; on Windows somente; requer plug-in)  <br/> |
|Permitir que outro usuário controle sua área de trabalho ou programa compartilhado  <br/> |&#x2714;|||||
|Adicione participantes anônimos (se ativado)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes pelo nome  <br/> |&#x2714;|&#x2714;||||
|Convidar participantes por número de telefone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Convidar participantes por email  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usar reuniões de áudio discado  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Iniciar uma reunião do Meet Now  <br/> |&#x2714;|&#x2714;||||
|Gravar uma reunião  <br/> |&#x2714;|||||
|Adicionar e baixar anexos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Adicione e apresente arquivos do Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Navegar nos arquivos PowerPoint Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Adicionar e editar OneNote de reunião  <br/> |&#x2714;||Editar somente (não adicionar)  <br/> |Editar somente (não adicionar)  <br/> |Editar somente (não adicionar)  <br/> |
|Use um quadro de avisos  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Faça votações  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Upload arquivos para compartilhar com outras pessoas  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Programe uma reunião ou conferência  <br/> |Outlook ou Agendador do Skype for Business Web  <br/> |Outlook ou Agendador do Skype for Business Web  <br/> |Agendador do Skype for Business Web  <br/> |Agendador do Skype for Business Web  <br/> |Agendador do Skype for Business Web  <br/> |
|Gerenciador de QA&amp;  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Desabilitar o vídeo do participante  <br/> |&#x2714;|||||
|Desabilitar o IM de reunião  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Mudo de público  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Tornar todos participantes  <br/> |&#x2714;|||||
|Produzir Reunião do Skype Transmissão  <br/> |&#x2714;|||||
   
 &#x2776; Participantes não podem controlar áreas de trabalho compartilhadas pelo Skype for Business para Mac, Lync para Mac 2011 ou Communicator para usuários mac 2011. Isso também não funcionará para Skype for Business Web App no Max OSX.
  
 &#x2777; Para Skype for Business Online, esse recurso requer Conferência PSTN da Microsoft, Exchange Unificação de Mensagens ou um provedor de audioconferência de terceiros.
  
 &#x2778; O cliente do Lync para Mac 2011 não pode exibir as apresentações do Microsoft Office 2013 PowerPoint quando elas foram compartilhadas em uma conferência pelo Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conhecidos e solução de problemas
<a name="BKMK_Conferencing"> </a>

Para usuários finais, a [ajuda online](https://aka.ms/smahelp) para esses aplicativos está prontamente disponível. Os profissionais de TI devem estar cientes dos seguintes problemas:
  
- Se o usuário estiver em uma rede não configurada para atender aos requisitos de [rede, muitos](meetings-clients.md#Network) recursos do aplicativo poderão ou não funcionar e talvez não possam se conectar à reunião.
    
- Alguns usuários podem ter computadores administrados pela empresa com permissão desabilitada para instalar aplicativos. para esses usuários, nenhum aplicativo é uma opção, mas os usuários de [smartphones](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [tablets](https://products.office.com/skype-for-business/download-app?tab=tabs-2) podem ser capazes de instalar clientes móveis baratos que podem usar para participar de reuniões.
    
    Outros problemas de instalação também são [abordados nos tópicos de ajuda](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Os usuários podem ver um aviso de firewall na primeira vez que executarem o aplicativo de reuniões. Eles podem ser solicitados a abrir portas para otimizar a experiência, e isso pode exigir privilégios de Administrador no computador que podem não ter. O aplicativo ainda deve funcionar e o usuário pode recusar com segurança a abertura das portas solicitadas. 
    
- Você deve ter [ActiveX habilitado sem filtragem](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) no Internet Explorer, mesmo que o IE não seja seu navegador padrão. No Skype for Business Web App, um controle ActiveX , um pequeno módulo que adiciona recursos adicionais a um aplicativo Web ou outro programa, é necessário para compartilhamento de áudio, vídeo e tela.
    
- Para que alguns recursos Skype for Business Web App funcionem corretamente, você deve permitir que o navegador [salve cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) em seu computador ou dispositivo.
    
- Talvez seja necessário ativar [o suporte javaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) no navegador para que alguns recursos Skype for Business Web App funcionem conforme o esperado.
    
### <a name="aes-support"></a>Suporte ao AES 

A partir do Skype for Business Server 2015 CU5, o AES não tem suporte para o ASP.NET 4.6 e isso pode fazer com que o aplicativo de reuniões do Skype falhe no início. [Os requisitos criptográficos devido ASP.NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) têm mais detalhes.
  
## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Implantar clientes baixáveis da Web em Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo Skype Reuniões](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
