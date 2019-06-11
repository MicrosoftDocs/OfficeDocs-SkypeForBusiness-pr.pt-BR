---
title: Como as fotos do usuário são exibidas no Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Como as fotos do usuário são exibidas no Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-08-25_

**Resumo:** As fotos do usuário exibidas no Lync Client podem ser diferentes dependendo de qual recurso do Lync você está usando, como quando está em uma conferência ou um chat de mensagem instantânea.

O Lync 2010 introduziu a capacidade de incluir uma foto com o seu perfil do Lync que é exibido para outros usuários do Lync. Você também pode escolher se deseja ou não exibir fotos para seus contatos no cliente do Lync. No Lync 2013, suporte para fotos de alta resolução para usuários. Este tópico descreve como o Lync Client Obtém e exibe as fotos do usuário, onde as imagens são armazenadas, as limitações para cada fonte de imagem e como as fotos do usuário são usadas por diferentes serviços do Lync.

<div>

## <a name="planning-considerations"></a>Considerações de planejamento

Você deve considerar o seguinte ao planejar a implementação do suporte para fotos de usuários.

  - O suporte para foto de usuário de alta definição requer que a caixa de correio do usuário esteja localizada no Exchange 2013 e a conta de usuário do Lync esteja no pool do Lync 2013.

  - Só há suporte para fotos de usuários de alta definição em um ambiente no qual o Lync Server 2013 e o Exchange 2013 são usados.

  - Os usuários com caixas de correio no Exchange 2010 sempre usarão o atributo **ThumbNailPhoto** do AD DS como a origem da foto do usuário.

  - Uma foto do usuário armazenada como o atributo **ThumbNailPhoto** do AD DS não será exibida para contatos externos/federados.

  - Se as fotos dos contatos do usuário estiverem armazenadas no AD DS, o arquivo de imagem usado será limitado a 96 × 96 pixels e não mais do que 100 KB de tamanho de arquivo.

  - Se a conectividade entre o Lync Server e o Exchange Server for perdida, o **ThumbNailPhoto** de baixa resolução do usuário do AD DS será exibido e somente para usuários internos.

  - Fotos de usuário de alta resolução são exibidas em reuniões do Lync 2013 quando um alto-falante ativo não está habilitado para vídeo. Além disso, mover o mouse sobre a foto em miniatura na Galeria mostrará a foto de alta resolução.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Fotos do usuário no Lync 2010

No cliente do Lync 2010, você pode escolher entre duas opções para exibir uma foto do seu perfil, a **imagem corporativa padrão** e **mostrar uma imagem de um endereço Web**.

<div>

## <a name="default-corporate-picture"></a>Imagem empresarial padrão

Quando você escolhe a opção **padrão de imagem corporativa** , o Lync Obtém a foto exibida para você nos serviços de domínio do Active Directory. A imagem usada é a imagem definida como o valor do atributo **ThumbNailPhoto** nos serviços de domínio Active Directory. Esse é o mesmo arquivo usado pelo Exchange para exibir imagens no Outlook.

As considerações sobre o uso de imagens dos serviços de domínio Active Directory incluem o seguinte:

  - Só há suporte para imagens com dimensões de até 96 pixels por 96 pixels. O tamanho do arquivo da imagem é limitado a 100 KB.

  - Por padrão, os usuários podem alterar a imagem usada para o atributo **ThumbNailPhoto** , mas não diretamente pelo cliente do Lync. Você pode desabilitá-lo por meio dos serviços de domínio Active Directory.

  - As imagens armazenadas nos serviços de domínio Active Directory não são exibidas para contatos externos à sua organização, mesmo que sejam contatos federados.

  - Em grandes organizações, armazenar e recuperar as imagens para um grande número de usuários pode afetar o tamanho e o desempenho do banco de dados dos serviços de domínio Active Directory.

  - As dimensões de imagem limitada e o tamanho do arquivo significam que apenas imagens de baixa resolução podem ser usadas.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Como os usuários gerenciam suas fotos de usuários nos serviços de domínio do Active Directory

O usuário não pode alterar a imagem usada no perfil dos serviços de domínio Active Directory diretamente pelo cliente do Lync 2010. Elas podem usar uma das seguintes opções para fazer isso, se disponíveis:

  - **Os usuários do SharePoint Server**   podem carregar uma foto em "meu site" em um servidor do SharePoint e, em seguida, [Configurar a sincronização de perfil no SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) para sincronizar a foto com o atributo **ThumbNailPhoto** no domínio do Active Directory Aos.

  - **Foto armazenada em URL**   publicamente acessível os usuários podem configurar a foto do usuário especificando uma URL publicamente acessível para a imagem que desejam usar. A imagem deve ser acessível publicamente sem uma senha. A imagem armazenada no endereço Web especificado é transferida para outros usuários por meio da categoria de cartão de visita nas informações de presença. Quando o cliente do Lync precisa exibir uma foto do usuário, ele recupera a imagem do endereço Web especificado.

  - **Cmdlets do Exchange 2010 para administradores do Windows PowerShell**   podem executar o cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) no Shell de gerenciamento do Exchange 2010 para gerenciar o atributo **ThumbNailPhoto** . Quando as imagens são importadas com cmdlets do Exchange 2010, o tamanho do arquivo limita-se a 10 KB.

  - **Ferramentas de terceiros**   os usuários podem carregar apenas suas próprias fotos para o atributo **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Mostrar uma imagem de um endereço Web

Quando você escolhe a opção **mostrar uma imagem de um endereço Web** , o Lync Obtém a imagem no endereço que você inserir e a exibe para a foto do usuário no Lync.

As considerações para usar imagens de um endereço da Web incluem o seguinte:

  - Os limites de tamanho de arquivo são determinados pelo atributo **MaxPhotoSizeKB** na política do cliente, definido com o cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) . O limite de tamanho padrão é 30 KB. O valor máximo é 100 KB. Não há restrição na resolução da imagem, mas se você tentar usar um arquivo de imagem que excede o limite de tamanho, ele não será baixado para os clientes do Lync. Você pode definir o valor como 0 para desativar a utilização de todas as fotos do usuário no Lync.

  - As fotos do usuário de um endereço da Web podem ser vistas por contatos federados externos.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gerenciando fotos do usuário com cmdlets da política do cliente

No Lync Server 2010, as configurações de política do cliente são configuradas com os cmdlets CsClientPolicy. As configurações de política definidas são enviadas aos clientes por meio do provisionamento em banda. Os dois parâmetros dos cmdlets CsClientPolicy que determinam a experiência de foto do usuário são **DisplayPhoto** e **MaxPhotoSizeKB**. O parâmetro de provisionamento em banda correspondente para **DisplayPhoto** e **MaxPhotoSizeKB** é chamado de superutilização. **** Os valores para **** o parâmetro superusage são enviados aos clientes por meio do **endpointConfiguration** **Provision**. Consulte [visão geral das políticas e configurações do cliente](http://go.microsoft.com/fwlink/?linkid=507470) para obter mais informações.

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
<th>Fonte de imagem</th>
<th>Configurações do cliente do Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Não fotográfico</p></td>
<td><p>nenhuma</p></td>
<td><p><strong>Não mostrar minha imagem</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Imagem empresarial padrão</strong></p></td>
</tr>
<tr class="odd">
<td><p>Fotos</p></td>
<td><p>Endereço Web</p></td>
<td><p><strong>Mostrar uma imagem de um endereço Web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Como o cliente do Lync 2010 Obtém fotos

No Lync 2010, as fotos do usuário são gerenciadas no servidor pelo serviço de catálogo de endereços. O Lync Client Obtém as fotos do usuário consultando o serviço de consulta à Web do catálogo de endereços (ABWQ) no servidor, que é exposto por meio do serviço Web de expansão de lista de distribuição. O cliente recebe o arquivo de imagem e, em seguida, copia-o para o cache do usuário para evitar o download da imagem toda vez que precisar ser exibido. Os valores de atributo retornados da consulta também são armazenados na entrada de serviço de catálogo de endereços em cache para o usuário. O serviço de catálogo de endereços exclui todas as imagens armazenadas em cache a cada 24 horas, o que significa que pode levar até 24 horas para que as novas imagens do usuário sejam atualizadas no cache do servidor. Você pode forçar uma atualização para o cache usando o cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

As fotos do usuário incluídas no status de presença também têm um valor de hash associado que o cliente Lync usa para determinar se há uma imagem mais recente disponível. O cliente é notificado automaticamente sobre alterações no arquivo de imagem usado em status de presença.

<div class=" ">


> [!NOTE]  
> Como as fotos não são armazenadas no banco de dados GalContacts. DB, baixar fotos do usuário não depende da configuração <STRONG>AddressBookAvailability</STRONG> na política do cliente (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">set-CsClientPolicy</A>).



</div>

A consulta para o serviço ABWQ inclui os seguintes atributos:

  - **Keyhash**   o valor de hash dos dados binários da foto e é usado para determinar se a foto atual foi alterada.

  - **PhotoRelPath**   o caminho relativo para o arquivo de imagem armazenado no servidor.

  - ****   Fotodimensionamento do tamanho do arquivo de imagem em bytes.

  - **Timestamp**   a data e a hora em que o arquivo de imagem foi baixado pela última vez do servidor e copiado para o cache do cliente.

Em seguida, depois de recuperar o arquivo de imagem, o cliente do Lync 2010 compara os valores de atributo retornados da consulta com os valores de atributo recebidos pelo cliente de provisionamento em banda para ver se eles são diferentes. Se os valores forem diferentes, o cliente recuperará o arquivo de imagem do usuário conectado com uma solicitação HTTP GET.

Além disso, o cliente verifica com o servidor a cada 24 horas a partir do momento em que a versão em cache do arquivo de imagem foi criada para comparar o **** valor do atributo cohash no servidor com o valor no cliente. Se os valores forem diferentes, o cliente saberá que o arquivo de imagem foi alterado. Para obter o arquivo de imagem atualizado, o cliente consulta novamente o serviço ABWQ para atualizar o arquivo de imagem no cache do cliente com o arquivo de imagem no servidor, que também redefine o **carimbo de data/hora** no arquivo no cache do cliente.

Veja a seguir um exemplo de resposta a uma consulta para o serviço ABWQ:

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

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Fotos do usuário no Lync 2013

O Lync 2013 introduziu suporte para imagens de alta resolução para fotos do usuário. O Lync 2013 também inclui suporte para armazenar fotos do usuário na caixa de correio do usuário no Exchange 2013, que remove a resolução da imagem e as limitações de tamanho presentes no Lync 2010. As fotos do usuário no Lync 2013 podem ter até 648 pixels por 648 pixels com um tamanho de arquivo de até 20 MB. Fotos de alta resolução no Lync 2013 devem estar localizadas na caixa de correio do usuário no Exchange 2013 e têm suporte apenas com o cliente Lync 2013. Essa integração com o Exchange aproveita a nova estrutura de autorização incluída nas versões do 2013 do Lync, Exchange e SharePoint chamados OAuth.

Se o Exchange 2013 não for usado na sua implantação, o suporte para fotos do usuário é o mesmo que o Lync 2010. No entanto, as opções do usuário para escolher a foto a ser usada são diferentes no cliente do Lync 2013. No cliente do Lync 2013, os usuários podem selecionar **ocultar minha imagem** ou **mostrar minha imagem**. A opção **mostrar uma imagem de um site** não está disponível por padrão, mas pode ser habilitada ao atribuir uma política de cliente.

<div>

## <a name="hide-my-picture"></a>Ocultar minha imagem

As configurações para fotos do usuário estão na caixa de diálogo **Opções** no Lync 2013. Quando você escolhe **ocultar minha imagem**, nenhuma foto do usuário é exibida para você no cliente do Lync, mas sua foto ainda é exibida no seu cartão de visita e fora do Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostrar minha imagem

Quando você escolhe a opção **mostrar minha imagem** , sua foto do usuário é exibida no seu cliente do Lync e para outros usuários nas conversas do Lync. A imagem usada é aquela armazenada no AD DS.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Mostrar uma imagem de um site

A opção **Mostrar imagem de um site** torna-se disponível no Lync 2013 depois que uma política de cliente é definida para habilitá-la. A versão do cliente deve ser mais recente do que o 15.0.4535.1002, que é instalado com as [atualizações cumulativas do Lync: novembro de 2013](http://go.microsoft.com/fwlink/p/?linkid=509908). Os usuários podem precisar fazer logout e, em seguida, retornar novamente para ver as alterações no cliente.

Você pode definir a política de cliente para habilitar a opção **Mostrar imagem de uma configuração de site** executando a política [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) no Shell de gerenciamento do Lync Server. Os cmdlets de exemplo a seguir demonstram como definir a política globalmente para todos os usuários em sua implantação:

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


Quando uma imagem é carregada para a caixa de correio do usuário, o Exchange cria automaticamente uma versão de resolução mais baixa da imagem que pode ser usada em aplicativos cliente. A foto do usuário também é atualizada no AD DS.

<div class=" ">


> [!NOTE]  
> Quando um arquivo de imagem é atualizado no AD DS, uma imagem de 48 x 48 pixel é criada e usada para o thumbnailPhoto no AD DS. Qualquer imagem existente será substituída. Portanto, se você adicionou uma imagem 96 x 96 ao AD DS, ela será substituída pela nova imagem do 48 x 48. Isso é importante apenas que você tem usuários em seu ambiente usando clientes do Lync 2010, pois esses clientes obterão fotos de usuários do AD DS. Você pode importar imagens de 96 x 96 pixels para substituir aquelas criadas pelo AD DS se você tiver clientes do Lync 2010 em sua organização.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Suporte a fotos do usuário no Lync 2013

No Lync 2013, há suporte para três resoluções de imagens para fotos do usuário, conforme descrito na tabela a seguir. A imagem que é usada é determinada pela configuração de política do cliente atribuída aos usuários do Lync. Consulte "Gerenciando fotos do usuário com cmdlets de política de cliente" neste tópico para obter mais informações.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Resolução da imagem (pixels)</th>
<th>Aplicativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Usado se nenhuma imagem de resolução mais alta estiver selecionada</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Usado no Outlook Web App e no Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Usado no cliente da área de trabalho do Lync 2013 e no Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Qualquer usuário com uma caixa de correio habilitada no Exchange 2013 pode carregar uma imagem diferente, incluindo fotos de alta resolução, através do Outlook Web Access ou do Lync 2013 cliente opções. As configurações recomendadas para imagens usadas incluem:

  - **Resolução de imagem**   648 por 648 pixels

  - **Profundidade de cor**   de 24 bits

  - **Tamanho do arquivo de imagem**   de até 20 MB

  - **Formato de arquivo**   JPEG

Uma imagem JPEG típica de 24 bits de 648 pixels por 648 pixels tem um tamanho de arquivo de aproximadamente 240 KB, portanto, 1 MB de espaço de armazenamento é necessário para cada 4 fotos do usuário.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

