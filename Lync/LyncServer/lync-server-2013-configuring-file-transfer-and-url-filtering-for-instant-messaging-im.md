---
title: Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

A ferramenta inteligente de filtro de IM ajuda a proteger a implantação do Lync Server 2013 contra a disseminação das formas mais comuns de vírus com uma redução mínima para a experiência do usuário. Use o filtro de IM inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou perigosas de pontos de extremidade desconhecidos fora do firewall corporativo. Você pode configurar filtros especificando os critérios a serem usados para determinar o que deve ser bloqueado, como mensagens instantâneas contendo hiperlinks com prefixos e arquivos específicos com extensões específicas.

O filtro de IM inteligente fornece o seguinte:

  - Filtragem de URL aprimorada.

  - Filtragem de transferência de arquivos aprimorada.

A configuração do filtro de IM inteligente inclui o seguinte:

  - Configurar a filtragem de URL.

  - Configurar a filtragem de transferência de arquivos.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Como as opções de filtragem são aplicadas às mensagens instantâneas

Antes de implantar a ferramenta de filtro de mensagem de chat inteligente, você precisa entender como as opções de filtragem são aplicadas à medida que as mensagens são roteadas de um servidor do Lync Server 2013 para outro. A maneira como essas opções de filtragem são consistentes é consistente, independentemente de os servidores estarem localizados em uma única organização ou entre fronteiras organizacionais. Essa consistência se aplica à maneira como o aviso e o texto de aviso personalizados são inseridos em mensagens e enviados entre servidores.

<div>


> [!NOTE]
> O filtro de mensagem instantânea aumenta a quantidade de recursos de CPU necessários para processar URLs em uma mensagem. Esse aumento na demanda de CPU também afeta o desempenho do Lync Server.



</div>

Usando a página **filtro de URL** no grupo **mensagens instantâneas e presença** no painel de controle do Lync Server, você pode bloquear alguns ou todos os hiperlinks ou configurar um aviso. O aviso é inserido no início de uma mensagem instantânea que contém um hiperlink quando você escolhe a opção de **prefixo de hiperlink** **Enviar mensagem de aviso**.

Quando uma mensagem instantânea transita de um servidor para outro, as seguintes diretrizes gerais se aplicam:

  - Se um servidor bloquear uma mensagem instantânea (porque você marcou a caixa de seleção **Bloquear URLs com extensão de arquivo** na página **filtro de URL** ou porque você escolheu a opção de prefixo de **hiperlink** **Bloquear**hiperlinks), uma mensagem de erro será retornada para o cliente. Os servidores subsequentes não recebem esta mensagem instantânea.

  - Se um servidor (Server1) adicionar um aviso a uma mensagem de chat que contém um hiperlink ativo, um servidor subsequente (Server2) que receber essa mensagem instantânea ainda poderá executar uma ação diferente com base nesse hiperlink ativo presente na mensagem instantânea e bloquear o Envie uma mensagem instantânea ou adicione um aviso. Se Server2 estiver configurado somente para adicionar um aviso para esta URL, o aviso anterior adicionado pelo Server1 será removido, e o aviso configurado no Server2 será adicionado ao início da mensagem instantânea.

<div>


> [!NOTE]
> Se você estiver executando o Lync Server 2013 em um ambiente misto, o Live Communications Server 2005 com SP1 é a versão mínima necessária para usar o aplicativo filtro inteligente de IM. Não há suporte para o filtro de IM inteligente no Live Communications Server 2005 sem SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtragem de URL

As URLs são filtradas de acordo com o prefixo do hiperlink. Os exemplos a seguir são prefixos válidos:

  - www\*.

  - FTP.

  - http

Se você não configurar o filtro de mensagem instantânea para executar qualquer filtragem de URL, todas as URLs contidas em mensagens instantâneas serão passadas de forma não modificada pelo servidor. Se você configurar o filtro de mensagem instantânea para executar a filtragem de URL, as URLs nas mensagens instantâneas serão filtradas de acordo com as opções que você selecionar na caixa de diálogo **Editar Filtro de URL** ou **novo filtro de URL** .

  - **Habilitar filtro**   de URL essa opção habilita a filtragem de URL para a implantação global ou para o site que você selecionar.

  - **Bloquear URLs com a extensão**   de arquivo o filtro de mensagem instantânea bloqueia qualquer URL ativa da intranet ou da Internet que contém um arquivo com uma extensão listada em **extensões de tipo de arquivo a serem bloqueadas** na caixa de diálogo **Editar Filtro de arquivos** . Quando uma URL é bloqueada, uma mensagem de erro é exibida para o remetente. Quando selecionada, essa opção tem precedência sobre todas as outras opções de filtragem para qualquer extensão de arquivo definida em **extensões de tipo de arquivo a serem bloqueadas**.
    
    <div>
    

    > [!IMPORTANT]
    > A filtragem de extensões de arquivo limita-se a nomes de arquivo padrão. A filtragem pode não funcionar com extensões de arquivo inseridas em outros nomes.

    
    </div>

Para configurar como os hiperlinks são manipulados nas conversas de mensagens instantâneas, selecione uma das seguintes opções em **prefixo do hiperlink**:

  - **Não filtre**   URLs nas mensagens são enviadas pelo servidor. Quando você escolhe essa opção, a caixa de **mensagem permitir** é exibida. Na caixa de **mensagem permitir** , especifique o aviso que você deseja inserir no início de cada mensagem instantânea contendo hiperlinks. Este aviso pode consistir em no máximo 65535 caracteres.

  - **Bloquear**   hiperlinks a entrega de mensagens instantâneas com hiperlinks ativos é bloqueada pelo Lync Server, e uma mensagem de erro é exibida para o remetente.

  - **Enviar mensagem**   de aviso o Lync Server permite hiperlinks ativos em mensagens instantâneas, mas inclui um aviso. Quando você escolhe essa opção, a caixa de **mensagem de aviso** é exibida. Na caixa de **mensagem de aviso** , você deve digitar o aviso que deseja incluir com mensagens instantâneas que contenham hiperlinks válidos. Por exemplo, este aviso pode declarar os possíveis perigos de clicar em um link desconhecido, ou pode se referir às políticas e requisitos relevantes da sua organização. O aviso não pode ter mais de 65535 caracteres.

Se você selecionar **Bloquear** hiperlinks ou **Enviar uma mensagem de aviso**, as seguintes opções estarão disponíveis:

  - **Excluir hiperlinks da intranet local**   o filtro de mensagem instantânea bloqueia somente URLs da Internet. As URLs para locais na sua intranet são passadas de forma não modificada pelo servidor. No entanto, as URLs de intranet que os servidores individuais que executam o Lync Server passam dependem de quais tipos de sites locais são considerados parte da zona da intranet deles. Para verificar as configurações de zona da intranet de um servidor, consulte o procedimento "para configurar suas configurações de intranet no Internet Explorer" em [Modificar o filtro de URL padrão no Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtre esses**   prefixos de hiperlink para escolher quais prefixos deseja bloquear, clique em **selecionar**e, em seguida, no **prefixo selecionar Hiperlink**, adicione os prefixos à lista prefixos de **hiperlink** .
    
    Todos os prefixos exceto **href** devem terminar com um ponto ou dois-pontos, ou um asterisco seguido por um ponto. Prefixos válidos podem conter qualquer caractere no conjunto de caracteres de URL válidos, exceto o\*asterisco (). O conjunto de caracteres válidos para URL é \# \*: +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ\_ \` ^ abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtragem de transferência de arquivo

A filtragem de transferência de filtro afeta mensagens instantâneas e conferências. Em conferências, essas configurações afetam o recurso folheto no cliente do Office Live Meeting 2007 e os recursos de reprodução de multimídia.

<div>


> [!NOTE]
> O Lync Server também oferece opções de configuração de transferência de arquivo. Essa opção do lado do servidor é oferecida além dos controles do lado do cliente disponíveis no Lync Server.



</div>

Você pode filtrar transferências de arquivos durante conversas de mensagem instantânea, quando estiver usando o recurso folheto no cliente do Office Live Meeting 2007 e para recursos de reprodução de multimídia para todos os tipos de arquivos. Você pode definir as seguintes opções para controlar as transferências de arquivos:

  - **Habilitar filtro**   de arquivo esta opção habilita a filtragem de arquivo para a implantação global ou para o site que você selecionar.
    
    Ao habilitar o filtro de arquivo, você pode escolher uma das seguintes opções na **transferência de arquivos**:
    
      - **Bloquear tipos**   de arquivo específicos você especifica quais solicitações de transferência de arquivo são filtradas pelo servidor especificando uma lista de extensões de arquivo a serem bloqueadas. As entradas na lista podem conter todos os caracteres padrão, mas não o caractere curinga\*(). No cliente do Office Live Meeting 2007, o recurso folheto está habilitado, mas qualquer arquivo com essa extensão não pode ser carregado ou baixado. Se você marcar a caixa de seleção **Bloquear URLs com extensão de arquivo** nas configurações de um filtro de URL listado na guia **filtro de URL** , o filtro de URL usará essa mesma lista para bloquear hiperlinks ativos que contenham qualquer uma dessas extensões de arquivo. Para escolher quais tipos de arquivo você deseja bloquear, clique em **selecionar**e, em seguida, em **Selecionar tipo de arquivo**, adicione as extensões de tipo de arquivo à lista de extensões de tipo de **arquivo selecionadas** .
    
      - **Bloquear todos**   os servidores descarta todas as mensagens instantâneas que contêm solicitações de transferência de arquivo e retorna uma mensagem de erro para o remetente da solicitação. O recurso folheto no cliente do Office Live Meeting 2007 está desabilitado.

<div>


> [!IMPORTANT]
> A filtragem de extensões de arquivo limita-se a nomes de arquivo padrão. A filtragem pode não funcionar com extensões de arquivo inseridas em outros nomes.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Criar um novo filtro de URL no Lync Server 2013 para manipular hiperlinks em conversas de mensagens instantâneas](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando configurações de IM e de presença no Lync Server 2013](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

