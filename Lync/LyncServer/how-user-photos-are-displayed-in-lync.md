---
title: Como as fotos do usuário são exibidas no Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097262cc3a4ba4b56cd023bc5174d881426deff2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Como as fotos do usuário são exibidas no Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-25_

**Resumo:** As fotos do usuário exibidas no cliente do Lync podem ser diferentes dependendo de qual recurso do Lync você estiver usando, como quando estiver em uma conferência ou em um chat de mensagens instantâneas.

O Lync 2010 introduziu a capacidade de incluir uma foto com seu perfil do Lync que é exibido para outros usuários do Lync. Você também pode escolher se deseja ou não exibir fotos para seus contatos no cliente Lync. No Lync 2013, suporte para fotos de alta resolução para usuários. Este tópico descreve como o cliente do Lync Obtém e exibe fotos do usuário, onde elas estão armazenadas, as limitações de cada fonte de imagem e como as fotos do usuário são usadas por diferentes serviços do Lync.

<div>

## <a name="planning-considerations"></a>Considerações de planejamento

Você deve considerar o seguinte ao planejar a implementação do suporte para fotos do usuário.

  - O suporte a foto de usuário de alta definição exige que a caixa de correio do usuário esteja localizada no Exchange 2013 e a conta de usuário do Lync seja no pool do Lync 2013.

  - Fotos de usuário de alta definição têm suporte apenas em um ambiente onde o Lync Server 2013 e o Exchange 2013 são usados.

  - Os usuários com caixas de correio no Exchange 2010 sempre usarão o atributo **ThumbNailPhoto** do AD DS como a origem da foto do usuário.

  - Uma foto de usuário armazenada como o atributo **ThumbNailPhoto** do AD DS não será exibida para contatos externos/federados.

  - Se as fotos para contatos de usuários estiverem armazenadas no AD DS, o arquivo de imagem usado será limitado a 96 × 96 pixels e não mais do que 100 KB de tamanho de arquivo.

  - Se a conectividade entre o Lync Server e o Exchange Server for perdida, o **ThumbNailPhoto** de baixa resolução do usuário do AD DS será exibido e somente para usuários internos.

  - As fotos do usuário de alta resolução são exibidas nas reuniões do Lync 2013 quando um alto-falante ativo não tem vídeo habilitado. Além disso, mover o mouse sobre a foto em miniatura na Galeria exibirá a foto de alta resolução.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Fotos do usuário no Lync 2010

No cliente do Lync 2010, você pode escolher entre duas opções para exibir uma foto para seu perfil, **imagem corporativa padrão** e **Mostrar imagem de um endereço da Web**.

<div>

## <a name="default-corporate-picture"></a>Imagem empresarial padrão

Quando você escolhe a opção **padrão de imagem corporativa** , o Lync Obtém a foto exibida para você nos serviços de domínio do Active Directory. A imagem usada é a imagem definida como o valor do atributo **ThumbNailPhoto** nos serviços de domínio do Active Directory. Este é o mesmo arquivo usado pelo Exchange para exibir imagens no Outlook.

As considerações para o uso de imagens de serviços de domínio do Active Directory incluem o seguinte:

  - Somente imagens com dimensões até 96 pixels por 96 pixels são suportadas. O tamanho do arquivo da imagem está limitado a 100 KB.

  - Por padrão, os usuários podem alterar a imagem usada para o atributo **ThumbNailPhoto** , embora não diretamente pelo cliente do Lync. Você pode desabilitá-lo por meio dos serviços de domínio do Active Directory.

  - As imagens armazenadas nos serviços de domínio do Active Directory não são exibidas para os contatos externos à sua organização, mesmo que sejam contatos federados.

  - Em grandes organizações, armazenar e recuperar as imagens de um grande número de usuários pode impactar o tamanho e o desempenho do banco de dados dos serviços de domínio do Active Directory.

  - As dimensões de imagem limitada e o tamanho do arquivo significam que apenas imagens de baixa resolução podem ser usadas.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Como os usuários gerenciam suas fotos de usuário nos serviços de domínio do Active Directory

O usuário não pode alterar a imagem usada em seu perfil de serviços de domínio do Active Directory diretamente através do cliente Lync 2010. Eles podem usar uma das seguintes opções para fazer isso, se disponíveis:

  - **Os usuários do SharePoint Server**   podem carregar uma foto em "My site" em um SharePoint Server e, em seguida, [Configurar a sincronização de perfil no SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar a foto com o atributo **ThumbNailPhoto** nos serviços de domínio do Active Directory.

  - **Foto armazenada em URL**   publicamente acessível os usuários podem configurar sua foto de usuário especificando uma URL publicamente acessível para a imagem que eles desejam usar. A imagem deve estar publicamente acessível sem uma senha. A imagem armazenada no endereço da Web especificado é transferida para outros usuários por meio da categoria cartão de visita nas informações de presença. Quando o cliente do Lync precisa exibir uma foto do usuário, ele recupera a imagem do endereço da Web especificado.

  - **Os cmdlets do Exchange 2010 para administradores do Windows PowerShell**   podem executar o cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) no Shell de gerenciamento do Exchange 2010 no para gerenciar o atributo **ThumbNailPhoto** . Quando as imagens são importadas com os cmdlets do Exchange 2010, o tamanho do arquivo é limitado a 10 KB.

  - **Ferramentas de terceiros**   os usuários podem carregar apenas suas próprias fotos para o atributo **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Exibir uma imagem de um endereço Web

Quando você escolhe a opção **mostrar uma imagem de um endereço da Web** , o Lync Obtém a imagem no endereço inserido e a exibe para sua foto do usuário no Lync.

As considerações para usar imagens de um endereço da Web incluem o seguinte:

  - Os limites de tamanho de arquivo são determinados pelo atributo **MaxPhotoSizeKB** na política de cliente, definido com o cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) . O limite de tamanho padrão é 30 KB. O valor máximo é 100 KB. Não há restrição na resolução da imagem, mas se você tentar usar um arquivo de imagem que excede o limite de tamanho, ele não será baixado para os clientes do Lync. Você pode definir o valor como 0 para desabilitar a utilização de todas as fotos do usuário no Lync.

  - As fotos de usuários de um endereço da Web podem ser vistas por contatos externos federados.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gerenciando fotos do usuário com cmdlets de política de cliente

No Lync Server 2010, as configurações de política do cliente são configuradas com os cmdlets CsClientPolicy. As configurações de política configuradas são enviadas aos clientes por meio do provisionamento em banda. Os dois parâmetros dos cmdlets CsClientPolicy que determinam a experiência de foto do usuário são **DisplayPhoto** e **MaxPhotoSizeKB**. O parâmetro de provisionamento em banda correspondente para **DisplayPhoto** e **MaxPhotoSizeKB** é chamado de **fotousage**. Os valores para o parâmetro **fotousage** são enviados aos clientes por meio do **endpointConfiguration** **Provision**. Confira [visão geral das políticas e configurações do cliente](https://go.microsoft.com/fwlink/?linkid=507470) para obter mais informações.

O valor do parâmetro **DisplayPhoto** determina a origem da imagem de foto do usuário. Os valores com suporte estão incluídos na tabela a seguir.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor do parâmetro DisplayPhoto</th>
<th>Origem da imagem</th>
<th>Configurações do cliente Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>nenhuma</p></td>
<td><p><strong>Não exibe minha imagem</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Imagem empresarial padrão</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Endereço da Web</p></td>
<td><p><strong>Exibir uma imagem de um endereço Web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Como o cliente Lync 2010 recebe fotos

No Lync 2010, as fotos do usuário são gerenciadas no servidor pelo serviço de catálogo de endereços. O cliente Lync Obtém as fotos do usuário consultando o serviço de consulta à Web do catálogo de endereços (ABWQ) no servidor, que é exposto por meio do serviço Web de expansão de lista de distribuição. O cliente recebe o arquivo de imagem e, em seguida, copia-o para o cache do usuário para evitar o download da imagem cada vez que precisa ser exibida. Os valores de atributo retornados da consulta também são armazenados na entrada de serviço de catálogo de endereços em cache para o usuário. O serviço de catálogo de endereços exclui todas as imagens armazenadas em cache a cada 24 horas, o que significa que pode levar até 24 horas para que as novas imagens de usuário sejam atualizadas no cache do servidor. Você pode forçar uma atualização para o cache usando o cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

As fotos do usuário incluídas no status de presença também têm um valor de hash associado que o cliente Lync usa para determinar se há uma imagem mais recente disponível. O cliente é notificado automaticamente sobre alterações no arquivo de imagem usado no status de presença.

<div class=" ">


> [!NOTE]  
> Como as fotos não são armazenadas no banco de dados GalContacts. DB, baixar fotos do usuário não depende da configuração <STRONG>AddressBookAvailability</STRONG> na política do cliente (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">set-CsClientPolicy</A>).



</div>

A consulta para o serviço ABWQ inclui os seguintes atributos:

  - **O keyhash**   é o valor de hash dos dados de foto binários e é usado para determinar se a foto atual foi alterada.

  - **PhotoRelPath**   o caminho relativo para o arquivo de imagem armazenado no servidor.

  - **Fotosize**   o tamanho do arquivo de imagem, em bytes.

  - **Timestamp**   a data e a hora em que o arquivo de imagem foi baixado pela última vez no servidor e copiado para o cache do cliente.

Em seguida, após recuperar o arquivo de imagem, o cliente Lync 2010 compara os valores de atributo retornados da consulta com relação aos valores de atributo recebidos pelo cliente do provisionamento em banda para ver se eles são diferentes. Se os valores forem diferentes, o cliente recupera o arquivo de imagem do usuário conectado com uma solicitação HTTP GET.

Além disso, o cliente verifica com o servidor a cada 24 horas a partir do momento em que a versão em cache do arquivo de imagem foi criada para comparar o valor do atributo **keyhash** no servidor com o valor no cliente. Se os valores forem diferentes, o cliente saberá que o arquivo de imagem foi alterado. Para obter o arquivo de imagem atualizado, o cliente consulta novamente o serviço ABWQ para atualizar o arquivo de imagem no cache do cliente com o arquivo de imagem no servidor, que também redefine o **carimbo de data/hora** no arquivo no cache do cliente.

Veja a seguir um exemplo de resposta a uma consulta para o serviço ABWQ:
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Fotos do usuário no Lync 2013

O Lync 2013 introduziu suporte para imagens de alta resolução para fotos do usuário. O Lync 2013 também inclui suporte para o armazenamento de fotos do usuário na caixa de correio do usuário no Exchange 2013, que remove a resolução da imagem e as limitações de tamanho presentes no Lync 2010. As fotos do usuário no Lync 2013 podem ter até 648 pixels por 648 pixels com um tamanho de arquivo de até 20 MB. As fotos de alta resolução no Lync 2013 devem estar localizadas na caixa de correio do usuário no Exchange 2013 e são suportadas apenas com o cliente Lync 2013. Essa integração com o Exchange tira proveito da nova estrutura de autorização incluída nas versões 2013 do Lync, Exchange e SharePoint chamados OAuth.

Se o Exchange 2013 não for usado em sua implantação, o suporte para fotos do usuário é o mesmo que com o Lync 2010. No entanto, as opções de usuário para escolher a foto a ser usada são diferentes no cliente Lync 2013. No cliente Lync 2013, os usuários podem selecionar **ocultar minha imagem** ou **mostrar minha imagem**. A opção **mostrar uma imagem de um site** não está disponível por padrão, mas pode ser habilitada por meio da atribuição de uma política de cliente.

<div>

## <a name="hide-my-picture"></a>Ocultar minha imagem

As configurações das fotos do usuário estão na caixa de diálogo **Opções** no Lync 2013. Quando você escolhe **ocultar minha imagem**, nenhuma foto do usuário é exibida para você no cliente do Lync, mas sua foto ainda é exibida no cartão de visita e fora do Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostrar minha imagem

Quando você escolhe a opção **mostrar minha imagem** , sua foto do usuário é exibida no seu cliente do Lync e outros usuários em conversas do Lync. A imagem usada é aquela armazenada no AD DS.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Mostrar uma imagem de um site

A opção **Mostrar imagem de um site** fica disponível no Lync 2013 depois que uma política de cliente é configurada para habilitá-la. A versão do cliente deve ser mais recente do que o 15.0.4535.1002, que é instalado com as [atualizações cumulativas do Lync: novembro de 2013](https://go.microsoft.com/fwlink/p/?linkid=509908). Talvez os usuários precisem fazer logout e voltar novamente para ver as alterações no cliente.

Você pode definir a política de cliente para permitir que **mostre a imagem de uma configuração de site** executando a política [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) no Shell de gerenciamento do Lync Server. Os cmdlets de exemplo a seguir demonstram como definir a política globalmente para todos os usuários em sua implantação:

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


Quando uma imagem é carregada para a caixa de correio do usuário, o Exchange cria automaticamente uma versão de resolução inferior da imagem que pode ser usada em aplicativos cliente. A foto do usuário também é atualizada no AD DS.

<div class=" ">


> [!NOTE]  
> Quando um arquivo de imagem é atualizado no AD DS, uma imagem de 48 x 48 pixel é criada e usada para o thumbnailPhoto no AD DS. Qualquer imagem existente será substituída. Portanto, se você tiver adicionado uma imagem 96 x 96 ao AD DS, ela será substituída pela nova imagem de 48 x 48. Isso só é importante se você tiver usuários em seu ambiente usando os clientes do Lync 2010, pois esses clientes obterão fotos do usuário do AD DS. Você pode importar imagens de 96 x 96 pixels para substituir as criadas pelo AD DS se tiver clientes do Lync 2010 em sua organização.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Suporte de foto do usuário no Lync 2013

No Lync 2013, são suportadas três resoluções de imagem para as fotos do usuário, conforme descrito na tabela a seguir. A imagem usada é determinada pela configuração de política de cliente atribuída aos usuários do Lync. Consulte "Gerenciando fotos do usuário com cmdlets de política de cliente" neste tópico para obter mais informações.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolução de imagem (pixels)</th>
<th>Aplicativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Usado se nenhuma imagem de resolução superior estiver selecionada</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Usado no Outlook Web App e no Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Usado no cliente de área de trabalho Lync 2013 e Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Qualquer usuário com uma caixa de correio habilitada no Exchange 2013 pode carregar uma imagem diferente, incluindo fotos de alta resolução, através do Outlook Web Access ou do Lync 2013 Client Options. As configurações recomendadas para imagens usadas incluem:

  - **Resolução de imagem**   648 por 648 pixels

  - **Intensidade de cor**   de 24 bits

  - **Tamanho do arquivo de imagem**   de até 20 MB

  - ****   JPEG no formato de arquivo

Uma imagem JPEG de 24 bits típica de 648 pixels por 648 pixels tem um tamanho de arquivo de aproximadamente 240 KB, portanto, 1 MB de espaço de armazenamento é necessário para cada 4 fotos do usuário.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

