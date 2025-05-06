<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Alur Interaktif</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            text-align: center;
            padding: 20px;
            background-color: #0f172a;
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }
        h1 {
            color: #e0f2fe;
            margin-bottom: 20px;
            font-weight: 600;
        }
        p {
            margin-bottom: 20px;
            line-height: 1.7;
            color: #f1f5f9;
            max-width: 80%;
        }
        #sapa-js {
            padding: 12px 25px;
            font-size: 18px;
            border-radius: 10px;
            color: white;
            border: none;
            cursor: pointer;
            margin: 10px;
            transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            background-color: #3b82f6;
        }
        #sapa-js:hover {
            background-color: #2563eb;
            transform: translateY(-2px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }
        @media (max-width: 768px) {
            #sapa-js {
                width: 100%;
                margin: 10px 0;
            }
        }
    </style>
</head>
<body class="bg-gray-900 dark:bg-gray-900 text-gray-200">
    <h1 class="text-3xl font-semibold text-blue-400 dark:text-blue-400">Selamat Datang di Aplikasi Interaktif</h1>
    <p class="text-lg text-gray-300 dark:text-gray-300">Klik tombol di bawah ini untuk memulai alur interaktif:</p>
    <div class="flex flex-wrap justify-center gap-4 mt-4">
        <button id="sapa-js" class="bg-blue-500 hover:bg-blue-700 text-white font-bold rounded-md shadow-md">Mulai</button>
    </div>

    <script>
        const sapaJsButton = document.getElementById('sapa-js');
        const quotes = [
            "Hidup itu seperti mengendarai sepeda. Untuk menjaga keseimbanganmu, kamu harus terus bergerak maju.",
            "Satu-satunya cara untuk melakukan pekerjaan hebat adalah dengan mencintai apa yang kamu lakukan.",
            "Jangan pernah menyerah pada mimpi hanya karena waktu yang dibutuhkan untuk mencapainya. Waktu akan berlalu.",
            "Percayalah pada dirimu sendiri, dan seluruh dunia akan bersamamu.",
            "Masa depan milik mereka yang percaya pada keindahan mimpi mereka.",
            "Cobalah untuk menjadi pelangi di awan seseorang.",
            "Sukses bukanlah kunci kebahagiaan. Kebahagiaan adalah kunci kesuksesan.",
            "Apa pun pikiran manusia dapat konsep dan percaya, itu dapat dicapai.",
            "Batasan hanya ada dalam pikiran.",
            "Satu-satunya cara untuk melakukan pekerjaan hebat adalah dengan mencintai apa yang kamu lakukan.",
            "Orang yang mengatakan itu tidak dapat dilakukan sebaiknya tidak mengganggu orang yang sedang melakukannya.",
            "Hidup adalah apa yang terjadi ketika kamu sibuk membuat rencana lain.",
            "Untuk menulis tentang kehidupan pertama-tama kamu harus menjalaninya.",
            "Keberanian adalah rahmat di bawah tekanan.",
            "Tidak ada yang mustahil, kata itu sendiri mengatakan 'Aku mungkin!'",
            "Kamu tidak pernah terlalu tua untuk menetapkan tujuan lain atau untuk memimpikan mimpi baru.",
            "Untuk mengetahui semua adalah memaafkan semua.",
            "Kita semua hidup di bawah langit yang sama, tetapi kita tidak semua memiliki cakrawala yang sama.",
            "Pikiran adalah segalanya. Apa yang kamu pikirkan kamu menjadi.",
            "Dua jalan bercabang di hutan, dan aku mengambil jalan yang kurang dilalui, dan itu membuat semua perbedaan.",
            "Kita dapat menghadapi banyak kekalahan tetapi kita tidak boleh dikalahkan.",
            "Bukan tahun-tahun dalam hidupmu yang penting, tetapi kehidupan dalam tahun-tahunmu.",
            "Entah kamu menjalankan hari itu, atau hari itu menjalankanmu.",
            "Saya lebih suka menyesali hal-hal yang telah saya lakukan daripada menyesali hal-hal yang belum saya lakukan.",
            "Hiduplah seolah-olah kamu akan mati besok. Belajarlah seolah-olah kamu akan hidup selamanya.",
            "Satu-satunya batasan untuk pencapaian kita besok adalah keraguan kita hari ini.",
            "Pikiran yang telah diperluas oleh pengalaman baru tidak akan pernah bisa kembali ke dimensi lamanya.",
            "Jangan pergi ke tempat jalan dapat mengarah, pergilah ke tempat tidak ada jalan dan tinggalkan jejak.",
            "Penting untuk tidak melihat terlalu jauh ke depan. Ambil satu langkah pada satu waktu.",
            "Setiap anak adalah seorang seniman. Masalahnya adalah bagaimana tetap menjadi seniman saat kita tumbuh dewasa.",
            "Kita tidak melihat sesuatu sebagaimana adanya, kita melihatnya sebagaimana adanya kita.",
            "Apa yang ada di belakang kita dan apa yang ada di depan kita adalah masalah kecil dibandingkan dengan apa yang ada di dalam diri kita.",
            "Waktu yang kamu nikmati untuk disia-siakan bukanlah waktu yang terbuang sia-sia.",
            "Lakukan yang terbaik sampai kamu tahu lebih baik. Kemudian ketika kamu tahu lebih baik, lakukanlah yang lebih baik.",
            "Satu-satunya cara untuk keluar dari labirin adalah dengan memaafkan.",
            "Kita semua adalah bintang, dan kita pantas bersinar."
        ];

        function getRandomQuote(nama) {
            const randomIndex = Math.floor(Math.random() * quotes.length);
            return `${nama}, berikut adalah quote untuk Anda: "${quotes[randomIndex]}"`;
        }

        sapaJsButton.addEventListener('click', () => {
            Swal.fire({
                title: 'Halo Pengguna!',
                text: 'Silakan masukkan nama Anda:',
                input: 'text',
                inputPlaceholder: 'Masukkan nama Anda',
                confirmButtonText: 'Lanjutkan',
                showCancelButton: true,
                cancelButtonText: 'Batal',
                background: '#1e293b',
                color: '#ffffff',
                showClass: {
                    popup: 'animate__animated animate__fadeIn'
                },
                hideClass: {
                    popup: 'animate__animated animate__fadeOut'
                },
                customClass: {
                    title: 'text-xl font-semibold text-blue-400 dark:text-blue-400',
                    content: 'text-lg text-gray-300',
                    input: 'bg-gray-800 text-white border-gray-700 placeholder-gray-400',
                    confirmButton: 'bg-blue-600 text-blue-200 hover:bg-blue-700 font-bold rounded-md shadow-md px-6 py-3',
                    cancelButton: 'bg-gray-600 hover:bg-gray-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                },
                preConfirm: (nama) => {
                    if (!nama) {
                        Swal.showValidationMessage('Nama tidak boleh kosong!');
                    }
                    return nama;
                }
            }).then((result) => {
                if (result.isConfirmed) {
                    const nama = result.value;
                    const quote = getRandomQuote(nama);
                    Swal.fire({
                        title: 'Terima Kasih!',
                        html: `<div style="background-color: #f7f3ec; padding: 20px; border-radius: 10px; border: 1px solid #e0e0e0; margin-bottom: 10px;
                                     background-image: linear-gradient(to bottom, #f7f3ec 0%, #f7f3ec 50%, #eee 51%, #eee 100%);
                                     background-size: 100% 6px; /* Ketebalan garis */
                                     background-repeat: repeat-y;
                                     background-position: 0 0, 0 0, 0 3px, 0 3px; /* Jarak antar garis */
                                     ">
                                 <div style="background-color: #1e3a8a; color: #ffffff; padding: 15px; border-radius: 5px; text-align: center; margin-top: 10px; position: relative;">
                                     <span style="position: absolute; top: -10px; left: 50%; transform: translateX(-50%); width: 20px; height: 20px; background-color: #f43f5e; border-radius: 50%; border: 2px solid #ffffff;"></span>
                                     ${quote}
                                 </div>
                             </div>`,
                        icon: 'success',
                        confirmButtonText: 'OK',
                        background: 'transparent',
                        color: '#ffffff',
                        showClass: {
                            popup: 'animate__animated animate__fadeIn'
                        },
                        hideClass: {
                            popup: 'animate__animated animate__fadeOut'
                        },
                        customClass: {
                            title: 'text-xl font-semibold text-green-400 dark:text-green-400',
                            content: 'text-lg text-gray-300',
                            confirmButton: 'bg-green-500 hover:bg-green-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                        },
                    }).then(() => {
                        Swal.fire({
                            title: 'Bagaimana pendapat Anda?',
                            text: 'Apakah pesan ini bagus?',
                            showDenyButton: true,
                            showCancelButton: true,
                            confirmButtonText: 'Bagus',
                            denyButtonText: `Tidak`,
                            cancelButtonText: 'Batal',
                            background: '#4b5563',
                            color: '#ffffff',
                            showClass: {
                                popup: 'animate__animated animate__fadeIn'
                            },
                            hideClass: {
                                popup: 'animate__animated animate__fadeOut'
                            },
                            customClass: {
                                title: 'text-xl font-semibold text-blue-400 dark:text-blue-400',
                                content: 'text-lg text-gray-300',
                                confirmButton: 'bg-green-500 hover:bg-green-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                denyButton: 'bg-red-500 hover:bg-red-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                cancelButton: 'bg-gray-600 hover:bg-gray-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                            },
                        }).then((result) => {
                            if (result.isConfirmed) {
                                Swal.fire({
                                    title: 'Siapa Anda?',
                                    text: 'Perkenalkan diri Anda!',
                                    input: 'text',
                                    inputPlaceholder: 'Masukkan nama Anda',
                                    confirmButtonText: 'OK',
                                    background: '#6b7280',
                                    color: '#ffffff',
                                    showClass: {
                                        popup: 'animate__animated animate__fadeIn'
                                    },
                                    hideClass: {
                                        popup: 'animate__animated animate__fadeOut'
                                    },
                                    customClass: {
                                        title: 'text-xl font-semibold text-blue-400 dark:text-blue-400',
                                        content: 'text-lg text-gray-300',
                                        input: 'bg-gray-800 text-white border-gray-700 placeholder-gray-400',
                                        confirmButton: 'bg-blue-500 hover:bg-blue-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                    },
                                    preConfirm: (nama) => {
                                        if (!nama) {
                                            Swal.showValidationMessage('Nama tidak boleh kosong!');
                                        }
                                        return nama;
                                    }
                                }).then((result) => {
                                    if(result.isConfirmed){
                                         Swal.fire({
                                            title: 'Terima Kasih!',
                                            text: 'Senang berkenalan dengan Anda.',
                                            icon: 'success',
                                            background: '#8b5cf6',
                                            color: '#ffffff',
                                            showClass: {
                                                popup: 'animate__animated animate__fadeIn'
                                            },
                                            hideClass: {
                                                popup: 'animate__animated animate__fadeOut'
                                            },
                                            customClass: {
                                                title: 'text-xl font-semibold text-purple-400 dark:text-purple-400',
                                                content: 'text-lg text-gray-300',
                                                confirmButton: 'bg-purple-500 hover:bg-purple-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                            }
                                        });
                                    }
                                })
                            } else if (result.isDenied) {
                                Swal.fire({
                                    title: 'Coba hubungi orang terdekatmu!',
                                    text: 'Mungkin dia adalah orang yang selama ini menunggumu.',
                                    showCancelButton: true,
                                    confirmButtonText: 'Apakah kamu malu?',
                                    cancelButtonText: 'Coba klik ini!',
                                    background: '#9ca3af',
                                    color: '#ffffff',
                                     showClass: {
                                        popup: 'animate__animated animate__fadeIn'
                                    },
                                    hideClass: {
                                        popup: 'animate__animated animate__fadeOut'
                                    },
                                    customClass: {
                                        title: 'text-xl font-semibold text-indigo-400 dark:text-indigo-400',
                                        content: 'text-lg text-gray-300',
                                        confirmButton: 'bg-purple-500 text-sky-400 hover:bg-purple-700 font-bold rounded-md shadow-md px-6 py-3',
                                        cancelButton: 'bg-gray-600 hover:bg-gray-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                    },
                                }).then((result) => {
                                    if (result.isConfirmed) {
                                        Swal.fire({
                                            title: 'Kenapa Malu?',
                                            text: 'Jangan malu untuk mengungkapkan perasaanmu.',
                                            icon: 'warning',
                                            confirmButtonText: 'OK',
                                            background: '#a855f7',
                                            color: '#ffffff',
                                            showClass: {
                                                popup: 'animate__animated animate__fadeIn'
                                            },
                                            hideClass: {
                                                popup: 'animate__animated animate__fadeOut'
                                            },
                                            customClass: {
                                                title: 'text-xl font-semibold text-purple-400 dark:text-purple-400',
                                                content: 'text-lg text-gray-300',
                                                confirmButton: 'bg-purple-500 hover:bg-purple-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                            }
                                        });
                                    } else if (result.dismiss === Swal.DismissReason.cancel) {
                                        Swal.fire({
                                            title: 'Dia sering menghubungimu...',
                                            text: 'Tapi kamu lupa?',
                                            icon: 'question',
                                            confirmButtonText: 'OK',
                                            background: '#f9a8d4',
                                            color: '#ffffff',
                                             showClass: {
                                                popup: 'animate__animated animate__fadeIn'
                                            },
                                            hideClass: {
                                                popup: 'animate__animated animate__fadeOut'
                                            },
                                            customClass: {
                                                title: 'text-xl font-semibold text-pink-400 dark:text-pink-400',
                                                content: 'text-lg text-gray-300',
                                                confirmButton: 'bg-pink-500 hover:bg-pink-700 text-white font-bold rounded-md shadow-md px-6 py-3',
                                            },
                                            footer: '<a href="#" style="color: #ffffff;">Klik disini</a>'
                                        });
                                    }
                                });
                            }
                        });
                    })
                }
            });
        });
    </script>
</body>
</html>
