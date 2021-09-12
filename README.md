# CPPCSVParser
Parses CSV files in C++


// initialize the CSV Parser (csvPath is simply where the csv file is )
    csv::Parser file = csv::Parser(csvPath);
 // can use a loop like the following to access rows and columns, using [row] [ column] syntax.


    try {
        // loop to read rows of a CSV file
        for (int i = 0; i < file.rowCount(); i++) {

            // initialize a bid using data from current row (i)
            Bid bid;
            bid.bidId = file[i][1];
            bid.title = file[i][0];
            bid.fund = file[i][8];
            bid.amount = strToDouble(file[i][4], '$');

            //cout << bid.bidId << ": " << bid.title << " | " << bid.fund << " | " << bid.amount << endl;

            // add this bid to the end
            list->Append(bid);
        }
   //catches errors
    } catch (csv::Error &e) {
        std::cerr << e.what() << std::endl;
    }
}













