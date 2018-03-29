---
title: Planejar para clientes de reuniões (Web App e reuniões App)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Resumo: Profissionais de TI devem examinar os requisitos de suporte para o Skype para negócios Web App e Skype reuniões App durante o planejamento de Skype para Business Server 2015. Este artigo não se destina os usuários desses aplicativos.'
ms.openlocfilehash: 608a85e36d436bbcee21e4ed86dc9b5c815088ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planejar para clientes de reuniões (Web App e reuniões App)
 
**Resumo:** Profissionais de TI devem examinar os requisitos de suporte para o Skype para negócios Web App e Skype reuniões App durante o planejamento de Skype para Business Server 2015. Este artigo não se destina os usuários desses aplicativos.
  
Depois que você implementou Skype para Business Server, os usuários da organização provavelmente terá o Skype para instalado como parte do processo de implantação de cliente de negócios. 
  
No futuro, esses usuários podem criar reuniões e convidar usuários de fora da organização e os convidados da reunião não podem ter qualquer versão do Skype para o cliente de negócios. Quando os usuários clicam na URL de convite da reunião, a falta de um cliente será detectada e o convidado sem um Skype para o cliente de negócios será solicitado a baixar e instalar um cliente leve, somente para reuniões, portanto, eles poderão ingressar na reunião.
  
> [!NOTE]
> O Skype para negócios Web App e Skype reuniões App só estarão disponíveis quando você tentar fazer logon uma reunião sem ter uma Skype para negócios. Ajuda do usuário para esses aplicativos está em [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Pré-você não pode instalar qualquer um do Skype para negócios Web App ou aplicativo de reuniões do Skype, mas os usuários de [telefone inteligente](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e [tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podem conseguir instalar baratos clientes móveis, que eles podem usar para participar de reuniões.
  
Por padrão, o servidor que hospeda a reunião direcionará o usuário baixe e instale o Skype para negócios Web App ingressar na reunião. O Skype para negócios Web App está armazenado no servidor Front-End e obtém enviada para participantes da reunião. 
  
Iniciando com Skype Business Server CU5, Skype reuniões App está disponível como uma substituição para Skype para negócios Web App, mas fornecer o aplicativo de reuniões Skype requer configuração adicional descrita em [Habilitar Skype reuniões App substituir Skype para Negócios Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Se Skype reuniões App for habilitada, os usuários serão baixar a versão mais recente do aplicativo do Office 365 conteúdo entrega rede (CDN), em vez do seu Skype para Business server.
  
Skype reuniões App oferece uma experiência de navegador simplificado para baixar e instalar o aplicativo e ingressar em reuniões, incluindo a associação de um clique para usuários do Internet Explorer. Skype reuniões App também tem vários aprimoramentos sobre theSkype para negócios Web App para obter confiabilidade e a experiência da reunião. 
  
> [!NOTE]
> A partir do Skype para Business Server 2015 CU5 ou posterior, reuniões conduzidas usando Skype para Business Online não enviará mais um usuário sem clientes do Skype para negócios Web App, eles serão em vez disso enviadas Skype reuniões App. A partir do Skype para Business Server 2015 CU5 ou posterior, se você [Habilitar Skype reuniões App substituir Skype para negócios Web App (opcional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), usuários sem clientes vão ser enviado Skype App de reuniões em vez do Skype para negócios Web App. 
  
## <a name="software-requirements"></a>Requisitos de software 
<a name="OS-Browser"> </a>

Para usar o Skype para negócios Web App, um usuário deve ter um dos seguintes suportada combinações de navegador e sistema operacional. 
  
**Sistema operacional e navegador mínimo suportem para Skype para negócios Web App**


|**Sistema Operacional**|**Borda**|**32 e 64 bits do Internet Explorer 11 ou posterior**|**32-bit e 64 bits do Internet Explorer 10 ou posterior**|**32-bit e 64 bits do Internet Explorer 9 ou posterior**|**32-bit e 64-bit Version do Firefox 12. x ou posterior**|**32-bit e 64-bit Version do Chrome 18. x ou posterior**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |Sim & #x 2778; <br/> |
| Windows 8.1 & #x 2776; <br/> |N/D  <br/> |Sim  <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |Sim & #x 2778; <br/> |
| Windows 8 (baseado em Intel) & #x 2776; <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |N/D  <br/> |Sim  <br/> |Sim & #x 2778; <br/> |
|Windows 7 com SP1 & #x 2777; <br/> |N/D  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |Sim  <br/> |Sim & #x 2778; <br/> |
|Windows Server 2008 R2 com SP1 & #x 2777; <br/> |N/D  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |Sim & #x 2778; <br/> |
|macOS 10,8 e versões posteriores (baseado em Intel) & #x 2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sim  <br/> |Sim & #x 2779; <br/> |
   
& #x 2776; O Skype plug-in de navegador da Web App de negócios exige um plug-in compartilhamento específico para usar voz baseados em computador, vídeo, compartilhamento e exibição de compartilhamento de tela em andamento e outros recursos. Um participante da reunião recebe a opção de instalar o compartilhamento plug-in quando eles entrarem na reunião ou quando eles iniciam um desses recursos. No Windows 8 e Windows 8.1, o compartilhamento plug-in pode ser instalado somente se você estiver executando o Internet Explorer 10 ou 11 do Internet Explorer para a área de trabalho. Esses recursos não estão disponíveis para o Internet Explorer 10 ou o Internet Explorer 11.
  
& #x 2777; Em com suporte do Windows 7, Windows Server 2008 R2 e os sistemas operacionais Macintosh, todos os recursos estão disponíveis, inclusive voz baseados em computador, vídeo, visualização de aplicativos, compartilhamento de aplicativos, a exibição da área de trabalho e o compartilhamento da área de trabalho. Para usar esses recursos, é preciso instalar o plug-in assim que for solicitado. Observe que não há mais suporte para a versão 10.7 do Mac OS X.
  
& #x 2778; Acessando o Web App de cromo no Windows iniciará um pequeno programa que carrega o aplicativo Web em um quadro incorporado do Internet Explorer. Esse programa requer que uma das versões com suporte do Internet Explorer esteja instalada para que o aplicativo Web seja carregado corretamente.
  
& #x 2779; Acessando o Web App de cromo no Mac iniciará um pequeno programa que carrega o aplicativo Web em um quadro de Safari incorporado. Este programa requer uma com o suporte versões do Safari estar instalado para o aplicativo Web carregar corretamente.
  
> [!NOTE]
> Usuários do Office 365 podem usar o Internet Explorer 10 ou posterior com Skype para negócios. 
  
### <a name="skype-meetings-app"></a>Aplicativo Reuniões do Skype

O aplicativo de reuniões Skype é executado como um aplicativo em computadores usando o Windows 10, Windows 8.1, Windows 8, Windows 7, com 32 e 64 bits do Internet Explorer 11 ou posterior instalado. 
  
O aplicativo também executa no macOS sistemas operacionais 10.10 ou posteriores com nenhuma dependência de navegador específico. 
  
Para outras dependências, consulte [plataformas suportadas para o aplicativo de reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>Requisitos de hardware
<a name="OS-Browser"> </a>

Os requisitos de hardware são determinados pelo sistema operacional e pelo navegador. Os recursos de voz e de telefonia exigem um microfone e alto-falantes, fone de ouvido com microfone ou dispositivo equivalente compatível com o computador. Os recursos de vídeo exigem um dispositivo de vídeo compatível com o computador. Para obter informações detalhadas sobre o suporte de hardware de vídeo e qualidade de vídeo esperada, consulte [Skype para resoluções de vídeo de cliente de negócios](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisitos de rede
<a name="Network"> </a>

Se um usuário do Skype para negócios Web App ou aplicativo de reuniões do Skype experiências problemas de conexão de reunião, chances são a que infraestrutura de rede da sua organização não estiver configurada para suportar o Office 365, conforme descrito em [URLs do Office 365 e intervalos de endereços IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Esse é o caso se a reunião foi criada por um usuário do Skype para Business Online ou Skype para Business Server 2015. 
  
Se o usuário estiver em uma rede não configurada conforme descrito, muitos recursos de aplicativo podem ou não podem funcionar e podem não ser capazes de se conectar à reunião mudaram.
  
## <a name="supported-meetings-features"></a>Recursos de Reuniões com suporte
<a name="BKMK_Conferencing"> </a>

Esta tabela compara os recursos de reuniões disponíveis para os usuários do Skype para o cliente de negócios, Skype para negócios Web App, Skype reuniões App e Lync Web App. Lync Web App está listado para fins de comparação de recurso: um usuário só seria baixando e usando o Lync Web App se a reunião foi hospedada em um servidor do Lync 2013.
  

|**Recurso/capacidade**|**Skype para 2016 de negócios do cliente**|**Skype para negócios no cliente do Mac**|**Aplicativo de reuniões do Skype**|**Skype para negócios Web App**|**Lync Web App**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Adicionar áudio do computador  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |
|Adicionar vídeo  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(exige plug-in)  <br/> |
|Alternar o áudio a um telefone para participantes autenticados  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Alternar o áudio a um telefone para os participantes convidados  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Compartilhamento de tela baseado em vídeo  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png) (para reuniões hospedadas no Skype para Business Online somente) <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Somente visualização)  <br/> |||
|Usar os controles do apresentador na reunião  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Acessar a lista de participantes detalhada da reunião  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Participar de IM com vários participantes  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Definir mensagens instantâneas com alta prioridade  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Compartilhar a área de trabalho (se habilitado)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(exige plug-in)  <br/> |
|Compartilhar um programa (se habilitado)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |
|Assumir o controle da área de trabalho compartilhada de outro usuário ou programa  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(No Windows apenas; exige plug-in)  <br/> |
|Permitir que outro usuário assumir o controle do seu programa ou área de trabalho compartilhada  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Adicionar participantes anônimos (se habilitado)  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Convidar participantes por nome  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|Convidar participantes por número de telefone  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Convidar participantes por email  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Usar reuniões de áudio discadas  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|
|Iniciar uma reunião do tipo Reunir Agora  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|Gravar uma reunião  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Adicionar e baixar anexos  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Adicionar e apresentar arquivos do Microsoft PowerPoint  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Navegar por arquivos do Microsoft PowerPoint  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Usar e editar notas de reunião do OneNote  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||Somente editar (sem adicionar)  <br/> |Somente editar (sem adicionar)  <br/> |Somente editar (sem adicionar)  <br/> |
|Usar um quadro de comunicações  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Realizar votações  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Carregar arquivos para compartilhar com outras pessoas  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Agendar um reunião ou conferência  <br/> |Outlook ou Skype para Agendador da Web de negócios  <br/> |Outlook ou Skype para Agendador da Web de negócios  <br/> |Skype para Agendador da Web de negócios  <br/> |Skype para Agendador da Web de negócios  <br/> |Skype para Agendador da Web de negócios  <br/> |
|Q&amp;um gerente  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Desabilitar vídeo de participante  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Desabilitar mensagens instantâneas de reunião  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Ativar mudo da audiência  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Tornar todos participantes  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Produzir Transmissão de Reunião do Skype  <br/> |![marcação na lista de verificação](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
   
![ler nota de rodapé 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png) Os participantes não é possível controlar as áreas de trabalho que são compartilhadas por Lync para Mac 2011 ou Communicator para Mac 2011 usuários. Esses usuários podem controlar as áreas de trabalho compartilhadas pelos usuários do Windows. Isso também não funciona com o Skype for Business no Mac OSX.
  
![ler nota de rodapé 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png) Para Skype para Business Online, este recurso exige o Microsoft Conferencing de PSTN, Unificação de mensagens do Exchange, ou um 3rd provedor de serviços de audioconferência de terceiros.
  
![ler nota de rodapé 3](../../media/f58a4c2c-e4b3-4954-9eee-1d5f7a89da53.png) O Lync para Mac 2011 cliente não conseguem exibir apresentações do PowerPoint do Microsoft Office 2013, quando eles foram compartilhados em uma conferência pelo Skype para negócios Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemas conhecidos e solução de problemas
<a name="BKMK_Conferencing"> </a>

Para usuários finais, a [Ajuda online](https://aka.ms/smahelp) para esses aplicativos está prontamente disponível. Profissionais de TI devem estar cientes dos problemas a seguir:
  
- Se o usuário não estiver em uma rede configurado para atender aos [requisitos de rede](meetings-clients.md#Network), muitos recursos de aplicativo podem ou não podem funcionar e podem não ser capazes de se conectar à reunião mudaram.
    
- Alguns usuários podem ter corporativo administrados computadores com permissão desabilitada para instalar aplicativos. para esses usuários, nem app é uma opção, mas os usuários de [telefone inteligente](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e [tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) podem conseguir instalar baratos clientes móveis, que eles podem usar para participar de reuniões.
    
    Outros problemas de instalação também são abordados nos [Tópicos de ajuda](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Os usuários podem ver um firewall aviso na primeira vez que são executados no aplicativo de reuniões. Eles também podem ser solicitados para abrir as portas para otimizar a experiência e isso poderá exigir privilégios de administrador na máquina que eles podem não ter. O aplicativo ainda deverá funcionar e o usuário pode recusar com segurança abrir as portas solicitadas. 
    
- Você deve ter [o ActiveX ativado sem filtragem](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) no Internet Explorer, mesmo se IE não é seu navegador padrão. No Skype para negócios Web App, um controle ActiveX — um módulo pequeno que adiciona recursos adicionais para aplicativos da web ou outro programa — é necessária para áudio, vídeo e compartilhamento de tela.
    
- Para alguns recursos do Skype para negócios Web App funcionar corretamente, você deve permitir que seu navegador, para [Salvar cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) em seu computador ou dispositivo.
    
- Você pode precisa para [Ativar o JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) dá suporte no seu navegador para alguns Skype para recursos corporativos Web App funcionar conforme o esperado.
    
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisitos criptográficos devido ao ASP .NET 4.5

A partir do Skype para Business Server 2015 CU5, AES não é suportado para ASP.NET 4.6 e isso pode causar Skype App de reuniões não sejam iniciados. Se um cliente estiver usando o AES como o valor de validação de chave de máquina, você precisará redefinir o valor da chave de máquina SHA-1 ou outro algoritmo com suporte no nível do site Skype reuniões App no IIS. Se necessário, consulte [Gerenciamento de configuração do IIS 8.0 ASP.NET](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) para obter instruções.
  
Outros valores suportados são:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 Os valores AES, 3DES e MD5 não são permitidos, como costumavam no ASP.NET 4. [Aprimoramentos criptográficos no ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) tem mais detalhes.
  
## <a name="see-also"></a>Ver também
<a name="BKMK_Conferencing"> </a>

#### 

[Implantar clientes para download da Web no Skype para Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)
#### 

[Plataformas com suporte para o aplicativo de reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

