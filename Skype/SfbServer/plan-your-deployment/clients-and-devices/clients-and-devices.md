---
title: Planejar clientes e dispositivos
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/20/2018
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
ms.assetid: 95f0852e-391d-4345-985f-0a2da50491fa
description: 'Resumo: análise dos clientes e aplicativos com suporte para o Skype for Business.'
ms.openlocfilehash: bcb6cfdaa0797e46ebc01f551a46600577d4dc27
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220551"
---
# <a name="plan-for-clients-and-devices"></a>Planejar clientes e dispositivos

**Resumo:** Análise dos clientes e aplicativos com suporte para o Skype for Business.

O setor de força de hoje está constantemente no movimento. Os funcionários precisam se comunicar e colaborar se trabalhar no escritório corporativo, em locais regionais, em escritórios domésticos ou em trânsito. O Skype for Business Server oferece suporte a essas necessidades por meio de uma coleção de interfaces de cliente que você pode implantar para os usuários da sua organização. O planejamento elaborado garante que os funcionários recebam o que precisam e que o Skype for Business esteja disponível para eles, onde quer que estejam.

## <a name="available-clients"></a>Clientes disponíveis

O Skype for Business Server oferece suporte a vários tipos de clientes, incluindo software cliente instalado no computador, clientes baseados na Web e clientes para dispositivos móveis. Os clientes primários são introduzidos nesta seção, para obter uma lista detalhada de todos os clientes com suporte consulte [comparação de recursos de cliente de desktop para o Skype for Business server 2015](desktop-feature-comparison.md) ou [para o recurso cliente de desktop para o Skype for Business Server 2019](../../../SfBServer2019/plan/feature-comparison.md). Se você já usou uma combinação de clientes do Lync, observe que há [clientes herdados](clients-and-devices.md#Legacy) não suportados que são incompatíveis com o Skype for Business Server 2019. As atualizações são realizadas regularmente, portanto, verifique este tópico periodicamente para obter as informações mais recentes do cliente.

### <a name="skype-for-business-2019"></a>Skype for Business (2019)

O Skype for Business (2019) é o cliente de destaque completo recomendado para o Skype for Business Server 2015 e 2019. Consulte [acompanhar as atualizações mais recentes no Skype for Business](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) para obter uma descrição dos novos recursos. O suporte aos recursos do cliente é detalhado na [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md)e a documentação do usuário está na [ajuda do Skype for Business](https://support.office.com/Skype-for-business). Esse cliente é incluído quando um usuário instala o Microsoft 365 ou o Office 365.

Um cliente básico gratuito que oferece suporte A menos recursos também está disponível. Ambas as versões estão disponíveis para download no [download do Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3). As diferenças entre clientes completos e básicos são descritas na seção [limitações do cliente básico](desktop-feature-comparison.md#Full-Basic) .

### <a name="skype-for-business-2016"></a>Skype for Business 2016

O Skype for Business 2016 é um cliente completo para o Skype for Business Server 2015 ou 2019. Veja [o que há de novo no Skype for Business 2016](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) para obter uma descrição dos novos recursos. O suporte aos recursos do cliente é detalhado na [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md)e a documentação do usuário está na [ajuda do Skype for Business](https://support.office.com/Skype-for-business). Esse cliente é incluído quando um usuário instala o Office 365.

Um cliente básico gratuito que oferece suporte A menos recursos também está disponível. Ambas as versões estão disponíveis para download no [download do Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3). As diferenças entre clientes completos e básicos são descritas na seção [limitações do cliente básico](desktop-feature-comparison.md#Full-Basic) .

### <a name="skype-for-business-2015"></a>Skype for Business 2015

O Skype for Business 2015 é um cliente completo para o Skype for Business Server 2015 ou 2019. A interface de usuário do Skype for Business foi totalmente reprojetada e inclui recursos integrados recentemente, como monitor de chamadas, integração de diretórios do Skype, emoticons e muito mais. Para obter um resumo das alterações, confira [o Skype for Business agora, consulte What ' s New](https://support.office.com/en-in/article/aba02d7e-c801-4a82-bccd-e7207240f612). O suporte aos recursos do cliente é detalhado na [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md)e a documentação do usuário está na [ajuda do Skype for Business](https://support.office.com/Skype-for-business). Esse cliente é incluído quando um usuário instala o Office 365.

### <a name="skype-for-business-on-mac"></a>Skype for Business no Mac

O cliente do [Skype for Business no Mac](https://www.microsoft.com/download/details.aspx?id=54108) está disponível para download. Consulte [Skype for Business em Mac Client requirements](mac-requirements.md) para revisar os pré-requisitos.

### <a name="skype-for-business-for-mobile-devices"></a>Skype for Business para dispositivos móveis

Os clientes estão disponíveis para Windows Phone, iPhone/iPad e Android. Os usuários podem obtê-los em [baixar o Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3). O suporte a recursos para esses clientes é detalhado em [comparação de recursos do cliente móvel para o Skype for Business](mobile-feature-comparison.md).

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.

### <a name="online-meeting-add-in-for-skype-for-business"></a>Suplemento de reunião online para o Skype for Business

O suplemento de reunião online para o Skype for Business suporta o gerenciamento de reunião de dentro do cliente de mensagens e colaboração do Microsoft Outlook no Windows. O suplemento de reunião online para o software Skype for Business é instalado automaticamente com o Skype for Business.

### <a name="skype-for-business-web-app-and-skype-meetings-app"></a>Skype for Business Web App e aplicativo de reuniões do Skype

Se o Skype for Business não estiver instalado no computador de um usuário e o usuário clicar em um link de reunião em uma solicitação de reunião em um computador Windows, o aplicativo reuniões do Skype ou o Skype for Business Web App será instalado e aberto.  Aplicativo de reuniões do Skype é o cliente escolhido para participantes fora da sua organização. (Observe que, em um Mac, o Skype for Business no Mac será instalado e aberto.) Consulte [Plan for encontros clients (aplicativo Web e aplicativos de reuniões)](meetings-clients.md) para obter os requisitos para usar esses clientes.


### <a name="skype-for-business-web-scheduler"></a>Agendador da Web do Skype for Business

O [Skype for Business Agendador da Web](https://sched.lync.com) é uma ferramenta de gerenciamento e agendamento de reuniões baseada na Web para usuários do Skype for Business online que não têm acesso ao Microsoft Outlook, ou que estão em um sistema operacional não baseado no Windows. Com o Agendador da Web do Skype for Business, os usuários podem criar novas reuniões, modificar reuniões existentes e enviar convites usando seu programa de email preferido. A [documentação](https://support.office.com/article/Skype-for-Business-Web-Scheduler-3b24a211-6470-4a2d-81b7-22d9399d0fec?ui=en-US&amp;rs=en-US&amp;ad=US) do Agendador da Web do Skype for Business oferece mais detalhes.

### <a name="vdi-plugins"></a>Plugins de VDI

Um ambiente de infraestrutura de área de trabalho virtual (VDI) é usado em algumas organizações onde problemas de segurança e conformidade são especialmente confidenciais. O uso do Skype for Business com áudio e vídeo completos em uma conexão como o requer cargas pesadas de processamento de áudio e vídeo no cliente hospedado em uma área de trabalho virtual. Está disponível um software adicional de plug-in VDI que descarrega o processamento para o computador local do usuário final e reduz a carga na área de trabalho virtual. Consulte [Plan for Skype for Business in VDI Environments](vdi-environments.md) para obter detalhes sobre como usar esses plugins.

### <a name="microsoft-teams-rooms"></a>Salas do Microsoft Teams

As salas do Microsoft Teams é a última solução de conferência da Microsoft que usa uma interface familiar e é facilmente implantada e gerenciada, aproveitando o equipamento existente, como painéis LCD, para facilitar a instalação. As salas do Microsoft Teams usam um aplicativo UWP desenvolvido especificamente, executado em um Surface Pro 4 ou Surface pro em um modo de console (uma vez implantado o aplicativo UWP é o único aplicativo que será executado no dispositivo) e requer sua própria conta de dispositivo na sua implementação. O software é atualizado por meio do Windows Store e do Windows Update. Consulte https://aka.ms/MTRDocs para obter detalhes sobre o uso desses consoles de sala em sua implantação. 

### <a name="skype-for-business-on-surface-hub"></a>Skype for Business no Surface Hub

O Microsoft Surface Hub é um dispositivo de produtividade All-in-One destinado a debates, colaboração e apresentações. Ele tem sua própria iteração do cliente Skype for Business, documentado no [Guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

## <a name="choosing-your-organizations-preferred-client"></a>Escolher o cliente preferencial da sua organização
<a name="BK_client_choose"> </a>

Se sua organização comprou as licenças adequadas, escolha o cliente completo; caso contrário, escolha o cliente básico.

Os usuários podem instalar o cliente para si mesmos para [baixar o Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3). O cliente também é instalado quando os usuários instalam o Microsoft 365 ou o Office 365 no Windows. Se alguns dos seus usuários tiverem Macs, esses usuários terão um conjunto diferente de recursos, conforme descrito nas seções anteriores.

Alguns recursos disponíveis com o Skype for Business Server 2015 não estão disponíveis no Skype for Business online ou no Skype for Business Server 2019, confira [limitações da conta de usuário online ou híbrida para](desktop-feature-comparison.md#Online-Hybrid) as limitações da conta de usuário do 2015 ou do [online ou híbrido para 2019](desktop-feature-comparison.md#Online-Hybrid) . Os administradores do Skype for Business Online podem querer consultar a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) para obter informações sobre os diferentes planos disponíveis para eles.

 Antes de implantar ou atualizar para o Skype for Business, verifique quais clientes já estão em uso na sua organização. Use a [comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md) para entender o impacto de suporte de recursos nesses clientes. Isso pode ajudar você a comunicar alterações aos usuários, ajustar o processo de implantação e compreender totalmente os benefícios da atualização para o cliente mais recente.

## <a name="ways-to-deploy-the-client-to-your-users"></a>Maneiras de implantar o cliente em seus usuários
<a name="BK_User_Deploy"> </a>

Os instaladores de cliente estão disponíveis para instaladores de tipo MSI e clique para executar. A estratégia de manutenção do cliente do Skype for Business pode afetar suas escolhas, portanto, você deve compreender os seguintes pontos:

- Em geral, o Skype for Business não adiciona novos recursos aos clientes lançados anteriormente

- Em geral, o Skype for Business não planeja entregar novos recursos no MSI do Skype for Business após sua versão inicial. Os aprimoramentos MSI entre as versões serão, principalmente, a qualidade/segurança da natureza.

- A experiência de cliente mais recente e maior do Skype for Business será encontrada no instalador clique para executar do Skype for Business 2019.

Você pode fazer uma implantação personalizada do cliente, conforme descrito em [Customize Windows Client installation in Skype for Business Server](../../deploy/deploy-clients/customize-windows-client-installation.md). Os métodos de instalação são descritos com mais detalhes em [Deploy clients for Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md)

### <a name="click-to-run"></a>Clique para executar

Clique para executar é uma tecnologia de streaming e virtualização da Microsoft que você pode usar para instalar e atualizar produtos do Office, incluindo o Skype for Business. Esses recursos de streaming e virtualização têm base em tecnologias no Microsoft Application Virtualization (App-V). Clique para executar tem as seguintes vantagens:

- Instalação em fluxo do pacote do Office que resulta em um tempo de instalação curto

- Atualizações e patches corrigidas

- Ocupa menos espaço em disco

- Licenciamento de base de usuário: 5 instalações por usuário

- Personalizável via editor de XML para a instalação de programas independentes

Talvez você queira usar a [ferramenta de implantação do Office](https://www.microsoft.com/download/details.aspx?id=49117) para este tipo de instalador.

As versões básica e completa do cliente (com opções de versões de 32 e 64 bits) estão disponíveis usando um instalador clique para executar, os usuários podem baixar o [Skype for Business em todos os seus dispositivos](https://products.office.com/skype-for-business/download-app?tab=tabs-3).

### <a name="msi"></a>MSI

MSI é um método de instalação mais tradicional, usado nos clientes do Skype for Business 2015 e 2016. Ele permite que você instale atualizações e patches manualmente, use licenciamento por volume e ativação e seja personalizável por meio da [ferramenta de personalização do Office](https://www.microsoft.com/download/details.aspx?id=49030). Você pode distribuir clientes aplicando políticas de grupo, usando o Microsoft Endpoint Configuration Manager ou usando uma ferramenta de terceiros.



## <a name="legacy-clients"></a>Clientes herdados
<a name="Legacy"> </a>

O Skype for Business Server 2019 e o Skype for Business online dão suporte aos seguintes clientes lançados anteriormente: Skype for Business 2016, Skype for Business 2015, Lync 2013.

O Skype for Business Server 2015 oferece suporte para os seguintes clientes lançados anteriormente: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Phone Edition e Lync 2010 Attendant. Para obter informações sobre esses clientes quando usados com outros servidores, consulte as [tabelas de comparação de clientes para o Lync server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) e as [tabelas de comparação de clientes para o Lync Server 2010](https://technet.microsoft.com/library/gg425836%28v=ocs.14%29.aspx).


## <a name="client-system-requirements"></a>Requisitos do sistema do cliente
<a name="Legacy"> </a>

Consulte os seguintes artigos para entender os recursos com suporte, plataformas, sistemas operacionais, navegadores e integração necessários para clientes do Skype for Business.

- [Planejar a experiência de cliente do Skype for Business para seus usuários](user-experience.md)

- [Comparação de recursos do cliente de desktop para o Skype for Business](desktop-feature-comparison.md)

- [Comparação de recursos do cliente móvel para o Skype for Business](mobile-feature-comparison.md)

- [Requisitos de cliente do Windows e suporte a software](windows-requirements.md)

- [Compatibilidade do Skype for Business com aplicativos do Office](compatibility-with-office.md)

- [Resoluções de vídeo de cliente do Skype for Business](video-resolutions.md)

- [Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)](meetings-clients.md)

- [Requisitos do sistema para o Skype for Business para Windows Phone](requirements-for-windows-phone.md)

- [Skype for Business nos requisitos do cliente Mac](mac-requirements.md)

- [Planejar salas do Microsoft Teams](skype-room-systems-v2-0.md)

- [Planejar o Skype for Business em ambientes de VDI](vdi-environments.md)

- Confira os [requisitos do sistema](https://products.office.com/office-system-requirements) para o hardware necessário.


## <a name="see-also"></a>Confira também

[Atualizações mais recentes para versões do Skype for Business que usam o Windows Installer (MSI)](../../sfb-client-updates.md)
