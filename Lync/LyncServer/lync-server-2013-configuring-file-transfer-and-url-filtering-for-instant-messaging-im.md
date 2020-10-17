---
title: Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM)
description: Configurar a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548347"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Configurando a transferência de arquivos e a filtragem de URL para mensagens instantâneas (IM) no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

A ferramenta inteligente de filtro de IM ajuda a proteger sua implantação do Lync Server 2013 contra a disseminação das formas mais comuns de vírus com menor degradação para a experiência do usuário. Use o Filtro de IM Inteligente para configurar filtros para bloquear mensagens instantâneas não solicitadas ou potencialmente prejudiciais de pontos de extremidade desconhecidos fora do firewall da empresa. Configure os filtros especificando os critérios que devem ser usados para determinar o que vai ser bloqueado, como mensagens instantâneas que tenham hiperlinks com prefixos específicos e arquivos com determinadas extensões.

O filtro de IM Inteligente fornece o seguinte:

  - Filtro avançado de URL.

  - Filtro avançado de transferência de arquivo.

A configuração do filtro de IM inteligente inclui o seguinte:

  - Configuração do filtro de URL.

  - Configuração do filtro de transferência de arquivo.

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>Como as opções de filtro são aplicadas a mensagens instantâneas

Antes de implantar a ferramenta de filtro de mensagens INSTANTÂNEAs inteligentes, você precisa entender como as opções de filtragem são aplicadas à medida que as mensagens são roteadas de um servidor do Lync Server 2013 para outro. A forma como essas opções de filtragem são aplicadas é consistente, quer os servidores estejam em uma única organização ou ultrapasse os limites organizacionais. Essa consistência se aplica à forma com que os textos personalizados de observação e aviso são inseridos em mensagens e enviados pelos servidores.

<div>


> [!NOTE]
> O filtro de mensagem instantânea aumenta a quantidade de recursos da CPU necessários para processar URLs em uma mensagem. Esse aumento na demanda da CPU também afeta o desempenho do Lync Server.



</div>

Usando a página de **filtro de URL** no grupo de **mensagens instantâneas e presença** no painel de controle do Lync Server, você pode bloquear alguns ou todos os hiperlinks ou configurar um aviso. Esse aviso é inserido no início de uma mensagem instantânea que contém um hiperlink quando você escolhe a opção **Enviar mensagem de aviso** em **Prefixo de hiperlink**.

Quando uma mensagem instantânea passa de um servidor para outro, as seguintes diretrizes gerais se aplicam:

  - Se um servidor bloqueia uma mensagem instantânea (por você ter marcado a caixa de seleção **Bloquear URLs com extensão de arquivo** na página **Filtro de URL** ou por você ter escolhido a opção **Bloquear hiperlinks** em **Prefixo de hiperlink**), uma mensagem de erro é devolvida ao cliente. Os servidores subsequentes não recebem essa mensagem instantânea.

  - Se um servidor (Servidor1) adiciona um aviso a uma mensagem instantânea que contém um hiperlink ativo, um servidor subsequente (Servidor2) que recebe essa mensagem ainda pode tomar uma ação diferente com base nesse hiperlink ativo, bloqueando a mensagem instantânea ou adicionando um aviso. Se o Servidor2 estiver configurado apenas para adicionar um aviso a esse URL, o aviso anterior adicionado pelo Servidor1 é removido, e o aviso configurado no Servidor2 é adicionado ao início da mensagem instantânea.

<div>


> [!NOTE]
> Se você estiver executando o Lync Server 2013 em um ambiente misto, o Live Communications Server 2005 com SP1 é a versão mínima necessária para usar o aplicativo de filtro de IM inteligente. O Filtro de IM Inteligente não é suportado no Live Communications Server 2005 sem o SP1.



</div>

<div>

## <a name="url-filtering"></a>Filtro de URL

Os URLs são filtrados de acordo com seu prefixo do hiperlink. Os exemplos a seguir são prefixos válidos:

  - www \* .

  - FTP.

  - http

Se você não configurar o filtro de mensagem instantânea para realizar o filtro de URL, todos os URLs presentes em mensagens instantâneas passam pelo servidor sem serem modificados. Porém, se você configurá-lo para realizar o filtro de URL, os URLs presentes em mensagens instantâneas são filtrados de acordo com as opções que você selecionou nas caixas de diálogo **Editar Filtro de URL** ou **Novo Filtro de URL**.

  - **Habilitar filtro**     de URL Essa opção habilita a filtragem de URL para a implantação global ou para o site que você selecionar.

  - **Bloquear URLs com extensão**     de arquivo O filtro de mensagem instantânea bloqueia qualquer URL ativa de intranet ou Internet que contenha um arquivo com uma extensão listada em **extensões de tipo de arquivo a serem bloqueadas** na caixa de diálogo **Editar Filtro de arquivo** . Quando um URL é bloqueado, uma mensagem de erro é exibida para o remetente. Quando selecionada, essa opção busca precedência em todas as outras opções de filtro para quaisquer extensões de arquivos definidas em **Extensões de tipos de arquivos a serem bloqueadas**.
    
    <div>
    

    > [!IMPORTANT]
    > A filtragem de extensões de arquivo está limitada aos nomes padrão. A filtragem pode não funcionar com extensões de arquivo incorporadas em outros nomes.

    
    </div>

Para configurar como hiperlinks são manuseados em conversas de mensagem instantânea, selecione uma das opções a seguir em **Prefixo de hiperlink**:

  - Não **Filtrar**     As URLs nas mensagens são enviadas pelo servidor. Quando você escolhe essa opção, a caixa **Permitir mensagem** aparece. Na caixa **Permitir mensagem**, especifique o aviso que você quer inserir no começo de cada mensagem instantânea que contenha hiperlinks. Esse aviso não pode ter mais que 65535 caracteres.

  - **Bloquear hiperlinks**     A entrega de mensagens instantâneas contendo hiperlinks ativos é bloqueada pelo Lync Server e uma mensagem de erro é exibida para o remetente.

  - **Enviar mensagem**     de aviso O Lync Server permite hiperlinks ativos em mensagens instantâneas, mas inclui um aviso. Quando você escolhe essa opção, a caixa de **mensagem de aviso** é exibida. Na caixa de **mensagem de aviso** , você deve digitar o aviso que deseja incluir com mensagens instantâneas contendo hiperlinks válidos. Por exemplo, este aviso pode declarar os possíveis perigos de clicar em um link desconhecido ou pode consultar as políticas e os requisitos relevantes da sua organização. O aviso não pode ter mais de 65535 caracteres.

Se você selecionar **Bloquear hiperlinks** ou **Enviar mensagem de aviso**, as seguintes opções estarão disponíveis:

  - **Excluir hiperlinks**     da intranet local O filtro de mensagens instantâneas bloqueia apenas URLs da Internet. Os URLs para locais dentro da sua intranet passam pelo servidor sem serem modificados. No entanto, as URLs de intranet que os servidores individuais que executam o Lync Server passam dependem de quais tipos de sites locais são considerados parte da zona da intranet. Para verificar as configurações da zona da intranet de um servidor, consulte o procedimento "para definir suas configurações de intranet no Internet Explorer" em [Modificar o filtro de URL padrão no Lync server 2013](lync-server-2013-modify-the-default-url-filter.md).

  - **Filtrar esses prefixos**     de hiperlink Para escolher quais prefixos você deseja bloquear, clique em **selecionar**e, em **selecionar prefixo de hiperlink**, adicione os prefixos à lista de **prefixos de hiperlink** .
    
    Todos os prefixos, exceto **href** devem terminar com ponto ou dois pontos, ou com um asterisco seguido por um ponto. Os prefixos válidos podem conter quaisquer caracteres no conjunto de caracteres de URL válidos, exceto o asterisco ( \* ). O conjunto de caracteres válidos da URL é: \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` abcdefghijklmnopqrstuvwxyz | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>Filtro de Transferência de Arquivo

O filtro de transferência de arquivo afeta as mensagens instantâneas e as conferências. Para as conferências, essas configurações afetam o recurso de folheto no cliente Office Live Meeting 2007 e os recursos de reprodução de multimídia.

<div>


> [!NOTE]
> O Lync Server também oferece opções de configuração de transferência de arquivo. Essa opção do lado do servidor é oferecida além dos controles do lado do cliente disponíveis no Lync Server.



</div>

Você pode filtrar transferências de arquivos durante as conversas com mensagens instantâneas, quando você estiver usando um recurso de folheto no cliente do Office Live Meeting 2007 e para recursos de reprodução de multimídia para todos os tipos de arquivo. Você pode definir as seguintes opções para controlar arquivos de transferência:

  - **Habilitar filtro**     de arquivo Essa opção habilita a filtragem de arquivos para a implantação global ou para o site que você selecionar.
    
    Quando você habilita o filtro de arquivo, você pode escolher uma das opções a seguir na **Transferência de arquivo**:
    
      - **Bloquear tipos**     de arquivo específicos Especifique quais solicitações de transferência de arquivo serão filtradas pelo servidor, especificando uma lista de extensões de arquivo a serem bloqueadas. As entradas na lista podem conter todos os caracteres padrão, mas não o caractere curinga ( \* ). No cliente do Office Live Meeting 2007 o recurso de folheto está habilitado, mas nenhum arquivo com essa extensão pode ser carregado ou baixado. Se você marcar a caixa de seleção **Bloquear URLs com extensão de arquivo** nas configurações listadas na guia **Filtro de URL**, o filtro de URL usa essa mesma lista para bloquear hiperlinks ativos que contenham qualquer uma dessas extensões de arquivos. Para escolher quais tipos de arquivos você quer bloquear, clique em **Selecionar**, depois clique em **Selecionar Tipo de Arquivo**, e adicione as extensões de tipos de arquivos à lista **Extensões de tipos de arquivos selecionadas**.
    
      - **Bloquear tudo**     O servidor descarta todas as mensagens instantâneas que contêm solicitações de transferência de arquivo e retorna uma mensagem de erro ao remetente da solicitação. O recurso de folheto do cliente do Office Live Meeting 2007 será desabilitado.

<div>


> [!IMPORTANT]
> A filtragem de extensões de arquivo está limitada aos nomes padrão. A filtragem pode não funcionar com extensões de arquivo incorporadas em outros nomes.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Modificar o filtro de transferência de arquivo padrão no Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [Criar um novo filtro de transferência de arquivo no Lync Server 2013 para um site específico](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Modificar o filtro de URL padrão no Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)

  - [Criar um novo filtro de URL no Lync Server 2013 para lidar com hiperlinks em conversas de IM](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

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

