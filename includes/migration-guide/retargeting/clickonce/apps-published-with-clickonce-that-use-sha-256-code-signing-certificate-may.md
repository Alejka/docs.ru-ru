### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="25e89-101">Приложения, опубликованные с помощью ClickOnce с использованием сертификата подписи кода SHA-256, могут завершиться ошибкой в Windows 2003</span><span class="sxs-lookup"><span data-stu-id="25e89-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

|   |   |
|---|---|
|<span data-ttu-id="25e89-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="25e89-102">Details</span></span>|<span data-ttu-id="25e89-103">Исполняемый файл подписывается с помощью SHA256.</span><span class="sxs-lookup"><span data-stu-id="25e89-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="25e89-104">Ранее он подписывался с помощью SHA1 независимо от того, какой использовался сертификат подписи кода: SHA-1 или SHA-256.</span><span class="sxs-lookup"><span data-stu-id="25e89-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="25e89-105">Применение:</span><span class="sxs-lookup"><span data-stu-id="25e89-105">This applies to:</span></span><ul><li><span data-ttu-id="25e89-106">Все приложения, собранные с помощью Visual Studio 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="25e89-106">All applications built with Visual Studio 2012 or later.</span></span></li><li><span data-ttu-id="25e89-107">Приложения, собранные с помощью Visual Studio 2010 или более ранней версии в системах с установленной платформой .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="25e89-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span></li></ul><span data-ttu-id="25e89-108">Кроме того, при наличии .NET Framework 4.5 или более поздней версии манифест ClickOnce также подписывается с помощью SHA-256 для сертификатов SHA-256 независимо от версии .NET Framework, в которой проводилась компиляция.</span><span class="sxs-lookup"><span data-stu-id="25e89-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>|
|<span data-ttu-id="25e89-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="25e89-109">Suggestion</span></span>|<span data-ttu-id="25e89-110">Изменение подписи исполняемого файла ClickOnce влияет только на системы Windows 2003. Требуется установка KB 938397. Изменение подписи манифеста с SHA-256, даже если целевая платформа приложения — .NET Framework 4.0 или более ранней версии, вводит зависимость среды выполнения для .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="25e89-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>|
|<span data-ttu-id="25e89-111">Область</span><span class="sxs-lookup"><span data-stu-id="25e89-111">Scope</span></span>|<span data-ttu-id="25e89-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="25e89-112">Edge</span></span>|
|<span data-ttu-id="25e89-113">Версия</span><span class="sxs-lookup"><span data-stu-id="25e89-113">Version</span></span>|<span data-ttu-id="25e89-114">4.5</span><span class="sxs-lookup"><span data-stu-id="25e89-114">4.5</span></span>|
|<span data-ttu-id="25e89-115">Тип</span><span class="sxs-lookup"><span data-stu-id="25e89-115">Type</span></span>|<span data-ttu-id="25e89-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="25e89-116">Retargeting</span></span>|
