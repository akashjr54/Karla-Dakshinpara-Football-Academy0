# করড়া দক্ষিণপাড়া ফুটবল একাডেমি — ওয়েবসাইট

## কী কী করা যাবে
- Public website: খেলোয়াড়, গ্যালারি, স্লাইডার, নোটিশ ও যোগাযোগ দেখা।
- Admin Panel: Firebase Email/Password দিয়ে লগইন করে খেলোয়াড় যোগ/এডিট/মুছুন, ছবি আপলোড, স্লাইডার/নোটিশ যোগ এবং হোমপেজের লেখা পরিবর্তন।
- ছবি Firebase Storage-এ থাকবে, তথ্য Firestore-এ থাকবে।

## গুরুত্বপূর্ণ: প্রথমবার সেটআপ
এই ZIP সরাসরি Firebase config ছাড়া লাইভ ডেটা দেখাবে না। একবার Firebase সেটআপ করতে হবে।

1. https://console.firebase.google.com খুলে Google account দিয়ে একটি project তৈরি করুন।
2. Project-এর Build > Authentication > Get started > Email/Password চালু করুন।
3. Authentication > Users > Add user থেকে নিজের Admin email ও শক্তিশালী password তৈরি করুন। ওয়েবসাইটের HTML-এ password লিখবেন না।
4. Build > Firestore Database > Create database তৈরি করুন।
5. Build > Storage > Get started চালু করুন।
6. Project Overview-এর ⚙️ Project settings > Your apps > Web app (</>) থেকে Web App তৈরি করে Firebase config কপি করুন।
7. `index.html` খুলে `const firebaseConfig`-এর PASTE_ মানগুলো নিজের config দিয়ে বদলান।
8. `firestore.rules` এবং `storage.rules` ফাইলে `YOUR_ADMIN_EMAIL`-এর জায়গায় Authentication-এ তৈরি করা Admin email লিখুন। Firebase Console-এর Firestore > Rules এবং Storage > Rules-এ যথাক্রমে কপি করে Publish করুন।

## GitHub Pages-এ প্রকাশ
1. GitHub-এ নতুন Public repository তৈরি করুন।
2. এই ফোল্ডারের সব ফাইল repository-তে Upload files দিয়ে আপলোড করে Commit changes করুন।
3. Repository > Settings > Pages > Deploy from a branch > main > /(root) > Save নির্বাচন করুন।
4. কিছুক্ষণ পর Pages-এর দেওয়া ওয়েবসাইট লিংক খুলুন।

## নিরাপত্তা
- Admin password কখনো `index.html` বা GitHub-এ লিখবেন না।
- `YOUR_ADMIN_EMAIL` দুটো Rules ফাইলেই একই Admin email দিয়ে বদলাবেন।
- শুধু বিশ্বস্ত ব্যক্তিকে Admin account দেবেন।
- Firebase Storage upload সীমা এখানে 8 MB রাখা হয়েছে।
- GitHub repository Public হলেও Firebase password প্রকাশ পাবে না; Firebase Rules-ই write access নিয়ন্ত্রণ করবে।

## সীমাবদ্ধতা / পরবর্তী উন্নয়ন
এটি একটি কাজ শুরু করার মতো responsive starter template। বর্তমান স্লাইডার একবারে প্রথম স্লাইডটি দেখায়; পরবর্তী সংস্করণে স্বয়ংক্রিয় carousel, একাধিক admin role, gallery edit/replace, match results, player detail page, map embed ও logo upload যোগ করা যেতে পারে।
